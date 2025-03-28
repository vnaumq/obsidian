[[Testing]]

A unit test is a way of testing the smallest piece of code that can be logically isolated in a software application. In most programming languages, that is a function, a subroutine, a method, or a property. The isolated part of the definition is important. In his book Working Effectively with Legacy Code, author Michael Feathers states that such tests are not unit tests when they rely on external systems. He writes, “If it talks to the database, it talks across the network, it touches the file system, it requires system configuration, or it can't be run at the same time as any other test."

Modern versions of unit testing can be found in frameworks like JUnit, or testing tools like [TestComplete](https://smartbear.com/product/testcomplete/overview/).Look a little further and you will find SUnit, the mother of all unit testing frameworks created by Kent Beck, and a reference in chapter 5 of The Art of Software Testing. Before that, it's mostly a mystery. We asked Jerry Weinberg about his experiences with unit testing -- "We did unit testing in 1956. As far as I knew, it was always done, as long as there were computers."

Regardless of when and where unit testing began, one thing is for sure. Unit testing is here to stay. Let's look at some more practical aspects of unit testing.

## What do unit tests look like?

A unit can be almost anything you want it to be -- a line of code, a method, or a class. Generally though, smaller is better. Smaller unit tests give you a much more granular view of how your code is performing. There is also the practical aspect that when you test very small units, your tests can be run fast; like a thousand tests in a second fast.

