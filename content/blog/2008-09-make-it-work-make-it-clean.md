A friend asked me if I wanted to have a look at the code he wrote for one of his projects at work. We've had some really interesting discussions on writing code in the past so I figured this would be an interesting experience as well.  I didn't know anything about this project, so I asked him if he could tell me what it was about.  His explanation wasn't really clear at first, so I figured: no problem, I'll just look over the code and it'll tell me what it does.

So I start looking at the code, and I just couldn't figure it out.  There was a lot of dealing with XML and XPath and some database stuff as well, but as to what the actual meaning of it all was, from a functionality point of view, I couldn't deduce it from reading the code.  Well, if I had spent a couple of hours on it then I probably would have, but from a 'quick read' it wasn't clear to me at all.  He did have tests, so he told me to look at those first.  They weren't that easy to read either because each test was testing a lot of stuff at once.  But they did verify that everything worked the way he intended it to work.

I showed him a piece of code that I wrote, to illustrate the differences in readability. He then showed me some code in his project that I had missed in my quick review.  From a readability perspective, it indeed looked very similar to how I write my code.  I then asked him why he didn't write the other code I had seen earlier in that way. He said "Well I haven't refactored that code yet, the stuff you just saw has been refactored already".  

That was really weird to me.  Personally, I try to write my code in a clean and readable manner from the start.  Obviously, you can't do everything as clean and readable as you'd like it to be while you're writing it the first time, so in those cases you'd usually start refactoring once the tests of that part of the code all pass.  His approach was different.  He wrote a lot of code just to make it all work, and he had the necessary tests in place to verify that it worked.  He knew that a lot of parts of the code were pretty bad, but he also knew that he could easily refactor the whole thing into clean code because he had all of his tests.

I told him that I think it's a lot easier if you either try to write it clean from the start, or start the refactoring much sooner.  Preferably, right after the tests of the part you're working on pass.  He said that he can't write it in a clean way from the start, and that he wanted to make the whole thing work before he'd start the refactoring.  When I asked him why that would be a good approach, he said it allowed him to put it in production much faster than if he were to write it all in in a clean way from the start.

And that was actually a very interesting statement. If we would both write the same system in the same time frame, our final solutions would probably be pretty similar in terms of readability and comprehensibility.  But with his "make it work, make it clean" approach, he would be able to start delivering immediate value to his customer much sooner than I would.  It only works because he has the discipline to actually clean up the code after he's put a working version in production.  

To avoid any confusion: it's not an approach that I would recommend. But I guess that for some people, there's nothing wrong with it.  If you have the discipline to clean up the code afterward, and you're able to deliver value to your customer very rapidly, can you really say something bad about it?  Also, don't think that this guy is a bad programmer because his first 'draft' of the code isn't all that good.  He knows more about clean code and valuable tests than most of the developers I've ever met.  He actually introduced me to TDD and Refactoring a few years back.  The way we use those techniques differs, but the final result will be pretty similar.  But his customers will probably enjoy the value of his projects sooner than mine.

As I had suspected, this experience did turn out to be very interesting :)