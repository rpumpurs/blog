---
published: false
---
## Program, Not Test

For some reason testing is generally seen as a boring, tedious and time consuming task. Well, I couldn't agree more, I would rather just write code and let somebody else do the testing, so actually, that *is* the solution that I am proposing!

[It seems](https://stackoverflow.com/questions/67299/is-unit-testing-worth-the-effort) that most of us agree that tests are useful, yet nearly every "real life" project that I have worked on hasn't had any test framework in place, let alone them being done "by the book". When trying to reason why there is not a natural gravitation towards automated tests and lack of motivation, I relate to my own experience. I used to think of tests as "nice to have" rather than clearly seeing the added value, I saw it as simply an extra work. Ironically, in reality, it turned out that not writing tests is even more work.

### The Idea

My thought is very simple - by opting to not write an automated test we forget that we are actually still doing the testing, only manual. This could be in many forms:
1. Clicking through a form on a website.
2. Calling a test script from the terminal.
3. Compiling the program and seeing debug output.
4. Etc.

In other words, we *are* actually doing the most boring part of programming. Even worse, we are doing it all the time - after every code change. At the extreme worse, we let the end customer do the testing.

I believe that unpleasant work should always be avoided, so in every situation I look for improvements and shortcuts to do things differently. Regarding writing tests, it means that in the end I actually end up testing less as test automation replaces the manual testing effort. The initial effort to write the test outweighs the manual testing which is done every time a new line of code is added.

### The Tester

In the first paragraph I suggested to let "somebody else" do the testing. To clarify, I don't intend to burden anyone, most importantly not the customer, with this wearisome task. Testing should be done in the following order by:
1. The author of the original code - in the form of automated tests as they are the least expensive when they are written together with the original code, because the intent of the code is the freshest when it is first typed up.
2. The CPU - lets make the computer do what it is best at - computation intensive work over and over again. No precious programmer time is used to run the automated tests.

### If It Works, Don't Touch It

Every programmer during their career has come across legacy code. Functionality that has been put together over multiple years and now works correctly (to an extent) in production. When you approach this code in order to change it, do you not ask to yourself, what sort of tests have been done to make sure this works? As we can imagine, multiple years of coding would have seen countless iterations where a new block of code was added, and some sort of test be made to make sure it works. Here often lies the problem, only half the work has remained with the project - the actual code, whereas all the clicking, scripting and debugging has simply vanished.

### Have Some Fun

Another benefit I find with writing automated tests is that it is much more fun! I am saying this to even just encourage the original author of the code who will be the only human participation in the actual testing. This point also goes back to my original idea regarding this post - lets program, not test. Writing the tests is basically programming, the test code has to be at the same quality standard as the actual code, so there is fun to be had in the challange to make the test code more readable and easier to use. Also, the programmer's mindset is opened up to new programming techniques like [TDD](https://en.wikipedia.org/wiki/Test-driven_development), and the general ability to understand and reason about software is increased. Finally, the tests serve as sort of a documentation. Writing documentation is mostly considered boring, it gets outdated, so again, tests solve both of those problems.

What more can be said, the goal is to be more productive while having fun.
