Just wanted to post a small reaction to Ayende's <a href="http://ayende.com/Blog/archive/2009/04/29/let-us-burn-all-those-pesky-util-amp-common-libraries.aspx">dismissal of Util & Common Libraries</a>.  In his post, Ayende goes over everything that Rhino.Commons (his own library) offers and why he's not using it anymore.  If you go over the list of everything in the library, I can definitely see why.  As Ayende says, it's the garbage bin for anything that he came up with in the past couple of years, regardless of how many projects would actually reuse each specific part.

At work we have also have something like this, though in some ways it's smaller in scale, and in some ways it offers a bit more than Rhino Commons.  A lot of it is based, or are further developed versions of, the infrastructural bits that I've posted on this blog in the last year.  We also have some other interesting things in there that my coworkers wrote.  We took the opposite direction however.  

We started off with putting these classes in each project where we could use them.  But since a lot of that stuff was still being modified or extended on a semi regular basis, we were constantly making the same changes or additions in multiple places, which violates the Don't Repeat Yourself principle.  Essentially, it was duplicate code, just spread in multiple projects.  Obviously, this brought along all of the same problems that duplicate code usually brings with it.  

So we set out to figure out to best way to deal with this, and I even <a href="/blog/2008/12/how-do-you-deal-with-common-infrastructure-code-for-multiple-projects/">asked you guys</a> about it.  We eventually ended up moving these bits to some sort of in-house library/framework that all (or most) of our applications now use.  While I was the one who was hesitant at first to go with a reusable library/framework (due to some bad experiences with it in the past), I'm now very glad we actually did do it. 

We did go for multiple assemblies (ie: web, silverlight, service layer, ...) instead of putting everything in one big assembly though we did try to follow my '<a href="/blog/2008/07/many-projects-dont-lead-to-a-good-solution/">one assembly per physical deployment</a>' rule.

Bugs get fixed in one place and one place only.  The only repetitiveness we have to endure when fixing a bug in the library is making sure we can merge the fix to previous versions and updating the referenced binaries in each project that uses it.  That's it.  New stuff only gets added when it's been proven to be useful in more than one project.  We don't just add new things like that, unless it really makes sense to do so.  

I think most of the problems that Ayende now sees with Rhino Commons can be avoided by splitting things up a bit more, and by being more restrictive as to what actually makes it into the library.  Versioning suddenly becomes pretty important as well.  These are all things that I always felt where somewhat missing with Rhino Commons.  That's not to criticize the project because I do think there's a lot of valuable stuff in there, but in it's current form it's just not very well suited to be reused by other projects.

Having said all that, I'm not saying that reusable libraries/frameworks are the best thing since sliced bread either.  They require a lot of discipline and it's easy to get tripped up simply by adding something or making a minor change where you didn't really think all of the consequences through.  But the downsides of dealing with these libraries are usually smaller than the downsides of having the same code spread out over multiple projects.