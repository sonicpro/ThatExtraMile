Concepts like Dependency Injection and using an Inversion Of Control container have gradually gotten more popular and accepted in the .NET world in the last 2 years or so. There are however still quite a few people who doubt the validity of these concepts. Quite a few of these people seem to think that Dependency Injection for instance is only useful to increase the testability of your code. I wanted to go over a real world example which shows a (IMO) huge benefit which can be solely attributed to thinking about loose coupling, using Dependency Injection and using an Inversion Of Control container.

I recently wrote a post about how you can use an <a href="/blog/2009/12/running-an-agatha-service-layer-in-process-without-wcf/" target="_blank">Agatha service layer fully in-process instead of having to host it in a different service through WCF</a>. The only reason why it’s so easy to do that, is because Agatha’s design makes heavy use of loose coupling and dependency injection. And obviously, it makes use of an Inversion Of Control container to manage the dependencies and to wire everything together.

There are basically 3 very important parts to Agatha. The first is the Request Processor. This class basically delegates the handling of each incoming request to its corresponding request handler. The other important parts are the Request Dispatcher (for synchronous client-side usage) and the Asynchronous Request Dispatcher (for asynchronous client-side usage). I'll just refer to these two classes as the request dispatchers for the rest of this post. When the service layer is hosted through a WCF service, the request dispatchers need to communicate with the Request Processor through a proxy (either a synchronous one, or an asynchronous one). It would’ve been very easy to tie the implementations of the request dispatchers directly to the implementation of the WCF proxies. If I had gone that way, I wouldn’t have been able to offer the ability to run the service layer in process though, since the request dispatchers would require the WCF proxies to be used. I could’ve hosted the WCF service in process, but that would really be overkill if you don’t really want to use WCF.

As easy as it would’ve been to tie the request dispatchers directly to the proxies, it was just as easy to make them depend on a slightly more abstract component. There are two interfaces to communicate with the Request Processor:

<script src="https://gist.github.com/3685672.js?file=s1.cs"></script>

Notice that there are no WCF attributes on these interfaces. I have two more WCF-enabled interfaces, namely the IWcfRequestProcessor and the IAsyncWcfRequestProcessor. They define the same methods as their non-WCF counterparts, but have all of the required WCF attributes placed on top of those methods.

Typically when creating (or generating) a WCF proxy, the proxy will only implement the interface of the service contract (in this case, that would be the IWcfRequestProcessor or the IAsyncWcfRequestProcessor interface). Any class that would want to use these proxies would then need an instance of that proxy to be able to communicate with the WCF service. In Agatha’s proxies, I chose a slightly different approach. They implement both the WCF interface as well as the none-WCF interface. Since the method definitions are identical, this doesn’t require any more work. Take a look at the class definitions of those proxies:

<script src="https://gist.github.com/3685672.js?file=s2.cs"></script>

As you can see, both proxy classes inherit from WCF’s ClientBase class and pass the WCF-specific interface as the generic type parameter to ClientBase. That means that these proxies can execute the WCF operations defined in the WCF-specific interface. These proxy classes also implement the original interfaces, which means that these proxies can be used by any class which requires an instance of IRequestProcessor and IAsyncRequestProcessor.

In Agatha, there is no class that directly uses either the RequestProcessorProxy or the AsyncRequestProcessorProxy class. Instead, the request dispatchers depend solely on IRequestProcessor or IAsyncRequestProcessor:

<script src="https://gist.github.com/3685672.js?file=s3.cs"></script>

The dispatchers never know exactly who they’re talking to. This means that they can communicate either through a WCF proxy, or the real Request Processor, depending on how your Inversion Of Control container is configured. That is a huge benefit because it gives you a tremendous amount of flexibility when it comes to how you want to use your service layer (in process, in another service, on another machine, whatever) and it really didn’t take any extra effort with regards to development time to achieve that flexibility. If I want to use Agatha with a different communication technology, then I could do so by simply creating implementations of the IRequestProcessor and IAsyncRequestProcessor interfaces which deal with the specifics of whatever that different communication technology might be. I would also have to change the way the implementations are registered with the Inversion Of Control container to make sure that the new implementations are used. But I wouldn’t have to change anything else.

In this case, dependency injection and loose coupling was not used to increase testability. The increased testability that comes from using this approach is <em>an added bonus</em>.</p>