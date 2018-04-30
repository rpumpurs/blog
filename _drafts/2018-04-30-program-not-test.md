---
published: false
---
## Program, Not Test

For some reason testing is generally seen as a boring, tedious and time consuming task. Well, I couldn't agree more, I would rather just write code and let somebody else do the testing, and actually, it is the solution that I am proposing!

The 'somebody else' could be:
1.  The cpu - lets make the computer do what they are the best at - computation intensive work over and over again. No precious programmer time is used to run the automated tests.
2. The authors of the original code - the automated tests are the least expensive when they are written together with the original code because the intent of the code is most fresh when it is first typed up.



I speak from my own experience as that is exactly what my thought process was when I started programming.

Nearly every programmer during their career has come across legacy code. Functionality that has been put together over multiple years and now works (within reason) in production. When you approach this code in order to change it, do you not ask to yourself, what sort of tests have been done to make sure this works? As we can imagine, multiple years of coding would have seen countless iterations where a new block of code would have been added, and some sort of test would be made to make sure it works. We can divide coding in two simple steps - writing the actual code, then making sure it works. Here lays the problem, only half the work has remained with the project - the actual code, whereas the other half (the major half, I would argue) has simply vanished.