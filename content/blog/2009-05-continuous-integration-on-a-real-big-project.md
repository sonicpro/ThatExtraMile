Some of you may remember a post of mine where I showed <a href="/blog/2009/03/continuous-failure/">the complete lack of attention that was being paid to the Continuous Integration of one of our projects</a>.  This particular project is pretty big.  The development of this project has gone on for years, and will keep going for years to come as it is a strategically important project for us.  The actual system is used internally by our company as well as a growing list of customers.

There are essentially 2 big problems with this project.  One is a mountain of legacy code with so much technical debt (due to <a href="/blog/2008/09/beware-the-evils-of-code-generation/">the evils</a> of <a href="http://www.codethinked.com/post/2009/05/05/Code-Generation-Should-be-the-Nuclear-Option.aspx">code generation</a>) it sorta resembles the current economic recession (as in: it'll take a <strong>long</strong> time to get everything sorted out).  The other problem is more a matter of organization.  We're a pretty small company and while we have great ideas for products, we simply can't assign a steady, stable team of developers to work on any of these projects on a continuous basis since we all often need to work on stuff that is simply more lucrative at that particular point in time.  The result is that this particular project typically has an ever rotating group of developers working on it, usually for short periods of time.  Some people work almost full-time on it, but that list is pretty limited. 

Not exactly the ideal situation for a large project to apply CI and other agile development practices to, right?  Luckily for us, we're quite stubborn and we try to make the best out of every situation.  So back when this project's CI success rate was <a href="/blog/2009/03/continuous-failure/">only showing a lack of success</a>, we all agreed to follow the <a href="/blog/2009/03/continuous-integration-101/">CI rules</a> and at this point, I'm pretty proud to be able to show you guys the following picture:

<img src="/postcontent/image001.png" alt="image001" title="image001" width="979" height="864" class="aligncenter size-full wp-image-1394" />

Note: we moved to <a href="http://www.jetbrains.com/teamcity/index.html">Team City</a> in July 2008 so I can't show you any earlier data than that.

Anyways, as you can see, after the dismal months of February and March, the success rate of the CI build gradually started improving again.  The average time to fix failing tests also decreased sharply.  We still have failing tests from time to time, but at least now they're all dealt with in a timely fashion.  We still have build failures, though those have decreased a lot as well and are always dealt with pretty soon now.  I'm not sure if this is because of my 'Continuous Bitching' whenever the build fails, or that everyone bought into the concept of CI again (for my own sake, I'll just assume that it's the latter instead of the former) but I'm pretty happy with the results that we're getting.

Also, take a look at the number of tests (we're at 16000+ now) and the duration of the build.  The build time is about 48 minutes on average now, which is obviously way above the recommended 10 minutes.  I'd love to see this go down to about 20 minutes (which I'd find very acceptable considering the size of the project) but that's gonna take a long while.  Of those 16000 tests, there are about 13000 tests that cover the legacy code and they <strong>all</strong> use the database.  And since those 13000 tests use a generated data layer, we can't just let it run on an in-memory database nor can we mock the database in those tests because all of that generated code, and pretty much everything that was written on top of it, is coupled more tightly than Siamese Twins.  We also lose a couple of minutes of build time due to some processing for an internal tool that we have to use.

So there you have it... the reason I wanted to post this is because when the topic of CI comes up, you always read about 'instant feedback' and really quick builds and things like that.  It's simply not always like that in the real world.  But with a bit of effort and focus, you can get many of the benefits that are usually attributed to CI, even on huge projects with lots of legacy code.  