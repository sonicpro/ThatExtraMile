Just a little heads-up to those reading this: this post is filed in the 'Rants' category.  I'm gonna rant about some stuff that I don't like, so if you don't like reading these kinds of posts, do both of us a favor and skip this one. 

I haven't been too happy with the .NET world lately.  I've always been somewhat critical of the .NET world, but generally, I felt it was one of the better environments to work in.  But there are some things that have been bothering me for a while now, and there are some recent developments that really made me think about the future of this platform.  First, I want to focus on the things that have been bothering me since the beginning.  After that, I'll discuss the problems that I expect in the future.

## One Ring To Rule Them All

As we all know, Microsoft has a tremendously large influence on how software gets developed in the .NET world.  For many companies, this is indeed quite convenient.  You can stick to the Microsoft Path (or should I say: the One Microsoft Way?) and you'll have all the guidance you can ask for.  They provide architectural and design guidance for everything from your database to your business layer to your service layer all the way to your presentation layer.  Unfortunately, a lot of that guidance is of a terribly low quality.  Follow their guidance and odds are pretty high that either your database implementation details are leaking through all the way to your screens, or that a lot of your business details are taken care of in the database.  Depending on how many Microsoft MVP's you've listened to, you might end up with both situations simultaneously.  

One of the most important goals of every piece of guidance and tooling that they provide is accessibility.  Lower-end developers should be able to use their products and their guidance and be able to build software of an acceptable quality.  Unfortunately, a lot of the mess that is produced on a daily basis in the .NET world is the result of that very same goal.  And the only people who are (knowingly) suffering from it are the higher-end developers.  They are the ones who have to deal with, and clean up the mess.  Customers and companies hardly ever realize how much money they're losing on this because this low standard for quality is apparently not only accepted in the .NET world, but also expected.   A lot of people simply don't know that the quality of software that we, the .NET community, produce on average is really low compared to other development communities.  But then again, that is naturally what you get when you want to lower the bar and try to get everyone involved with developing software.  You'd think that after over 50 years of history in this business, we'd have wised up to that fallacy by now, no?

The low quality of the guidance and the tools is the reason why I have started referring to the typical Microsoft recommended development practices and products as Fisher Price Development.  It's great if you're into toys, but if you wanna get serious, it's just not gonna cut it.  It wouldn't be so much of a problem if the vast majority of the .NET developer community wouldn't just blindly accept everything that Microsoft tells them to do or use.  Which brings me to my next point...  

## Developers, Developers, Developers!

There is a huge difference in quality between the higher-end .NET developers, and the lower-end.  The higher-end developers are generally more open-minded to what works in other development communities and want to learn from that.  And they want to take what they've learned and apply that in their .NET work.  The lower-end developers however will rarely venture beyond the approaches that Microsoft recommends.  The higher-end developers generally try to share their knowledge and experience with others, but in doing so, will waste a lot of time and effort going against the backlash they'll get from the lower-end developers.  The lower-end developers frequently accuse the higher-end developers for making things more complicated than they need to be, while they fail to realize that their initially simple solutions (as recommended by Microsoft of course) only leads to severe complications later on.  

If you think about it, it's pretty similar to the Matrix.  You've got a small minority of people who have noticed that something isn't quite right, took the red pill and are continuously going through hardship because of it.  On the other hand, you've got a group of people who'd choose the blue pill to go back to a world where they're being spoon-fed a reality that isn't quite real by a system that only wants to keep them in check so they remain in control.  

It's just not easy to be a .NET developer who values Continuous Improvement.  If you're not wasting time working with people who are quite content with Fisher Price Development, you're likely working for people who're telling you to use some of the Fisher Price Building Blocks because "It's Fisher Price! You can't go wrong with that!".  I've been in both situations in the past and it just drains so much energy from you.  If you're in neither situation, you are in a very small minority.

## The Road Ahead

So what exactly does the future of the .NET platform look like? Obviously, nobody knows.  I'll tell you what I expect to happen though.  I found it extremely telling that Microsoft is capable of putting resources on products like WebMatrix and LightSwitch (both of which are targeting the very-very-lower-end developers, or even non-developers) while at the same time, they are severely cutting back the resources for projects like IronRuby, IronPython and the DLR (which drew more interest from the higher-end developers than the lower-end developers).  So what exactly does that tell us?  I can only consider that to be a very clear message that the lower-end developers will always be the primary target of Microsoft, and that they really care less and less about the higher-end developers.  When it comes to guidance and tooling, they are continuously displaying that they either just don't get it, or that they just don't care.

So where does that lead us?  I think we're only going to get more and more low-quality software projects being developed in .NET due to the increased and continuous focus on the lower-end developers and the ever decreasing focus on keeping higher-end developers happy.  A lot of the higher-end developers will simply move to other platforms and communities.  Communities where sharing of knowledge and experience is encouraged, instead of hampered.  Communities where best practices are based on real world experience instead of being concocted in a few ivory towers by people who've been detached from real world projects for far too long.  Communities where there is less low-quality crap that needs continuous maintenance.  Communities where there is no One Ring To Rule Them All.