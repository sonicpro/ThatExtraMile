In the <a href="/blog/2009/09/must-everything-be-virtual-with-nhibernate-part-ii/">previous post</a> I showed a piece of code which suffers from 2 problems and asked you guys to spot both problems.  One of the problems was pointed out in the comments, but nobody mentioned the other one.

Once again, this is the code example:

<a href="/postcontent/transitive_persistence411.png"><img src="/postcontent/transitive_persistence411.png" alt="transitive_persistence41" title="transitive_persistence41" width="798" height="635" class="aligncenter size-full wp-image-1687" /></a>

Instead of making everything virtual, only properties that are eligible for lazy-loading have been made virtual.  Now, the line of code that is problematic is obviously the one where the DiscountPercentage of the customer backing field is accessed.  I will address using the field instead of the property later on in this post so bear with me for now.

There are 2 situations in which this code will fail badly.  The first situation is when you're dealing with a proxy of an Order.  If you have an uninitialized proxy of Order, and you call the non-virtual CreateOrderLine method then you will get a NullReferenceException because the proxy can't intercept the call to CreateOrderLine, and because it also can't intercept accessing the customer field, which will be null at that time.   This problem was correctly spotted by one of the people who left a comment.

The other problem is far worse, IMO.  Suppose you have a genuine instance of an Order object, but its reference properties haven't been loaded yet and are uninitialized proxies.  If there is no requirement for every public member of a proxy-able type to be virtual, then we can pretty much assume that the DiscountPercentage of the Customer class is also non-virtual.  Which means that with this code, we have no possible way of intercepting the call to the Customer's proxy's DiscountPercentage property.  Unfortunately, DiscountPercentage will have its default value of 0, so you won't get an exception... instead, the customer gets no discount even though its record in the database might have a discount set.

The possibility of running into one of these problems due to usage of an ORM and depending on how an object is loaded is simply unacceptable.  Some people commented on the usage of the customer backing field instead of the Customer property with a "then simply don't do that" response.  That's not an acceptable solution to this problem, it's a lame workaround at best.  There are plenty of reasons why people would use the backing field in their code instead of the property and if they run into this problem, they definitely will blame the ORM.  And rightfully so, I might add.