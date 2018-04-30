---
published: false
---
## Program, Not Test

For some reason testing is generally seen as a boring, tedious and time consuming task. Well, I couldn't agree more, I would rather just write code and let somebody else do the testing, so actually, it is the solution that I am proposing!

First I will need to clarify what I mean by it. The story is about automated - unit, integration etc.  - tests. I am trying to find reasons for why there seems to be so much resistance towards them. It [seems](https://stackoverflow.com/questions/67299/is-unit-testing-worth-the-effort) that we all agree that tests are useful, yet nearly every "real life" project that I have worked on hasn't had a proper test framework in place. Also, I have witnessed a lack of motivation from my co-workers to write tests. I can relate to this resistance and lack of motivation from my own experience as that is exactly what my thought process was when I started programming. I always thought of tests as "nice to have" rather than clearly seeing the added value.

### The Idea

My thought is very simple - by opting to not write an automated test we forget that we are actually still doing the testing, only manual. This could be in many forms:
1. Clicking through a form on a website.
2. Calling a test script from the terminal.
3. Compiling the program and seeing debug text output.
4. Etc.
In other words, we are doing the most boring part of programming.

I believe that boring work can nearly always be avoided, so in every situation I look for shortcuts to do things differently. Regarding writing tests, it means that in the end I actually end up testing less when I write automated tests. The initial effort outweighs the manual testing which is done every time a new line of code is added.

The object that will do the testing, or the 'somebody else' in the first paragraph, is:
1. The cpu - lets make the computer do what it is best at - computation intensive work over and over again. No precious programmer time is used to run the automated tests.
2. The author of the original code - the automated tests are the least expensive when they are written together with the original code because the intent of the code is most fresh when it is first typed up.

### If It Works, Don't Touch It

Nearly every programmer during their career has come across legacy code. Functionality that has been put together over multiple years and now works (within reason) in production. When you approach this code in order to change it, do you not ask to yourself, what sort of tests have been done to make sure this works? As we can imagine, multiple years of coding would have seen countless iterations where a new block of code would have been added, and some sort of test would be made to make sure it works. We can divide coding in two simple steps - writing the actual code, then testing it. Here lays the problem, only half the work has remained with the project - the actual code, whereas the other half (the major half, I would argue) has simply vanished if only manual tests have been done.

### The Passionate Programmer

Another benefit I find with writing tests is that it is much more fun! This point goes back to my original idea regarding this post - lets program, not test. Writing the test is actual programming, the test code has to be at the same quality standard as the actual code, so there is fun to be had in the challange to make the test code more readable and easier to use. Also, the programmer's mindset is opened up to new programming techniques like [TDD](https://en.wikipedia.org/wiki/Test-driven_development), and the general ability to understand and reason about software is increased. To conclude, the tests serve as sort of a documentation. Writing documentation is mostly considered boring, it gets outdated, so again tests solve both of those problems.

What more can be said, I choose to be more productive while having fun.