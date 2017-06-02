---
layout: post
author: domenique
---
The last couple of years I've noticed a shift in peoples viewpoint towards testing and in particular unit testing.
5 years ago, I was doing projects and no one even mentioned the word unit testing. Nowadays,
everyone wants to do unit testing in some form. Some projects in which I was involved required 100% code coverage,
 other's put the mark at 80%. I've never been that enthusiastic about any number, but the point is that we
 are doing some form of testing, be it TDD or testing after the facts.

The truth is, I haven't come across a unit-test suite which offered me one of the most important
thing it's supposed to give me: **confidence and quick feedback**. There is always something in the way:
either the test suite is too slow, or the tests are testing such a small part of a piece of functionality
that it does not give me the confidence that the application as a whole is working as it was intended.
Furthermore, most test suites I've come across seem to lack one more thing: **describing the behaviour of the code in an expressive way**.

# Some of the testing strategies and their implications
Most often, I see people employing the **one-test-method-per-public-method** strategy.
I guess that the reason that this strategy is seen the most is because most IDE's propose you to create
the skeleton for this automatically given that you already implemented the code. Usually,
when people realise that they can't test every branch of the code in one test, they end up making multiple
tests for the same method. This is not a bad thing, they are just adhering to the single assert rule.
The bigger problem for me is the fact that what they are testing **doesn't mean anything**. What's the added value
of testing some method which is being used by a piece of functionality to get the job done,
without knowing if the functionality as whole is working. Moreover, in a lot of cases, that method
that they are testing is only being used by the piece of functionality they should be testing as a whole.

When doing **TDD**, you won't come across this issue a lot. You write a unit test describing how you want the piece of functionality to behave,
after that, you write your implementation. Once the test is green, you get to choose whether you want to refactor the code,
or continue with the next test. Usually, the first couple of rounds don't require a refactoring phase. But then, all of the sudden,
you decide that your implementation is **becoming to big** and you start **refactoring**: you split up the implementation in a
bunch of smaller methods (*extract 'till you drop*), after which you realise that a bunch of those methods shouldn't be in that
class because you have **SRP violations**, so you extract them to a new class. While doing all of this, you occasionally rerun
your tests, which should remain green the whole time. Once you're happy with the results, you continue to write additional tests.
These short cycles keep on going until you have implemented the piece of functionality.

Now, imagine that you finished that piece of functionality, how will it look? Do you have one test method
for each method that you extracted? Or do you have one test class with **multiple tests covering a bunch of methods and classes**?
Imagine the test method names, and their contents... If you've done the job correctly it should be describing the behaviour
of that piece of functionality in the greatest detail possible.

Imagine that you have to adapt that piece of functionality six months after you wrote it and you wrote
 your tests using the *one-test-method-per-public-method* strategy. do you think it would take you longer then when you employed the TDD strategy?
Most of the projects (if not all..) I've worked on used some form of the first strategy, and believe me,
If you need to refactor a bunch of tests because you decided that you want to extract a few lines of code
out of one of those methods, you are in for a painful afternoon. If you're out of luck and the method is rather
big and has a lot of branches, you are set to adapt 10, 20 tests, and guess what, you didn't even change anything on a functional level.
The main reason for this is because your tests are highly coupled to your implementation.

# Blackbox vs Whitebox testing
**Blackbox** testing implies that you test the output of a piece of functionality by giving it some
input **without knowing anything about the internal workings** of functionality.
**Whitebox** testing is the inverse, it's like **pouring concrete over your implementation**, it makes sure
that you cannot freely change how something is implemented because you assert on how the code is supposed
to behave instead of what the results are.

When employing **TDD**, you are **forced to do Blackbox** testing simply because the implementation is not there yet.
This has the advantage that your tests cannot be highly coupled and that by consequence you are **free to refactor**
the implementation without having to change any of the tests.

When writing tests **after the facts**, you are constantly lured into doing Whitebox testing, **the definition of your unit will blur**,
and you are putting up **artificial boundaries** between classes that would not be there when doing TDD.
This results in tests that are highly coupled to the implementation and require a lot of mocks and stubs.
Basically, you are **not testing the functionality of your unit, but the structure of your code**. This style of
testing is often recognized by the excessive usage of Mocking frameworks like Mockito, EasyMock, PowerMock and simular
frameworks. While they serve their purpose in some circumstances, they are usually used for the wrong reasons. To me,
they should be used to mock out infrastructural parts of your applications, or pieces of functionality which tend to be
really slow resulting in bigger feedback loops.

#Conclusion
Although I don't have that much experience with TDD, I can honestly say that the quality of my test code has
improved drastically. I love the fact that I can refactor code without breaking my test suite. If I did brake it,
I'm sure that I've done something wrong, which is reassuring and gives me the confidence to play around with the code.