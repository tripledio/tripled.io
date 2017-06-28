---
layout: post
author: domenique
disqus: false
header-img: "img/patterns.jpg"
---

_SOLID_, The famous acronym coined by Micheal Feathers describing the first five principles of object oriented design composed by Robert C. Martin a.k.a Uncle Bob. What most people tend to forget is that __SOLID describes only five of the in total eleven principles of object oriented design__. These principles date all the way back to 1995, yes Uncle Bob is really that old :)

This post will briefly describe the well known SOLID principles, after which we will dive deeper into the 6 other, lesser known principles. This post will ultimately become a series, so do check back for follow-up articles.

# SOLID Principles

The SOLID principles are the first five principles of object oriented design and focus around class design.

- **S**ingle responsibility principle
- **O**pen closed principle
- **L**iskov substitution principle
- **I**nterface segregation principle
- **D**ependency inversion principle

# Single responsibility principle

<iframe width="560" height="315" src="https://www.youtube.com/embed/2k1uOqRb0HU" frameborder="0" allowfullscreen="">
</iframe>

__SRP__(Single Responsibility Principle) dictates that a class should have only **one responsibility and this responsibility should be fully encapsulated by the class**.

In the context of __SRP__, Uncle bob refers to a responsibility as being _a reason for change_. He concluded that if you can find more then one __motive for changing__ a class, then that class has more then one responsibility. Failing to adhere to this principle could result in _rigidity_ because clients of your class will be __forced to change for reasons they shouldn't__, on the other hand, applying this principle without looking carefully at the context of your application can have a negative effect and introduce needless complexity.

> The Single Responsibility Principle is one of the simplest of the principles, and one of the hardest to get right. Con-joining responsibilities is something that we do naturally. Finding and separating those responsibilities from one another is much of what software design is really about. Indeed, the rest of the principles we will discuss come back to this issue in one way or another.
>
> -- Uncle Bob, Agile Software Development. Principles, patterns and practices

# Open closed principle
OCP states that objects should be __open for extension__ and __closed for modification__. _Abstractions are the key here_, we usually make objects extensible by putting the right abstractions around them. However, this principle requires that the programmer is capable of __predicting the future__, how else is he able to know where to put the right abstractions? You cannot put abstractions everywhere otherwise you end up with complex and hard to maintain code.

Uncle Bob suggest that we only put an abstraction when we have to extend an object for the first time. This will make sure that we do not get burned by it again.

> Since Closure cannot be complete, it must be strategic. That is, the designer must choose the kinds of changes against which to close his desgin. He must guess at the most likely kind of changes, and then construct abstractions to protect him from those changes.
>
> -- Uncle Bob, Agile Software Development. Principles, patterns and practices

OCP is at the root of several heuristics and conventions that we know and use today such as _making all member variables private_, _avoiding Global state_ and _avoiding runtime type identification (RTTI)_. These heuristics and conventions are probably already quite familiar to you.

# Liskov substitution principle

> Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it.
>
> -- Barbara Liskov, Data Abstraction and Hierarchy

This principle simply states that as a client of an abstraction hierarchy, it should be possible to __use any of the sub types without knowing it__. The simplest violation is usually found when doing runtime type checking (RTTI) since this implies that the code needs to be aware of all the subtypes of that abstraction.However, there are more subtle violations of the LSP. the famous _square vs rectangle problem_ for example.

Bertrand Meyer's concept of __Design By Contract__ is closely related to the LSP. This principle explains that functions have pre and post conditions, __pre-conditions should be met before execution__ the function, __post-conditions are guaranteed after execution__ of the method. When redefining functions in derivative classes you should only __replace pre-conditions with a weaker one and post-conditions by a stronger one__. Or as Uncle Bob explains it:
> When using an object through its base class interface, the user knows only the preconditions and postconditions of the base class. Thus, derived objects must not expect such users to obey preconditions that are stronger then those required by the base class. That is, they must accept anything that the base class could accept. Also, derived classes must conform to all the postconditions of the base. That is, their behaviors and outputs must not violate any of the constraints established for the base class. Users of the base class must not be confused by the output of the derived class.
>
> -- Uncle Bob

# Interface segregation principle

Interface segregation states that it's __better to have many small interfaces instead of one general purpose one__. In other words, you should not be forced to implement or depend upon interfaces containing functions that you don't need. The ISP promotes low coupling and high cohesion. It also promotes the creation of __interfaces tailored to the clients rather then the implementations__.

> The ISP acknowledges that there are objects that require non-cohesive interfaces however it suggests that clients should not know about them as a single class. Instead, clients should know about abstract base classes that have cohesive interfaces.
>
> -- Uncle Bob

# Dependency inversion principle
> A. HIGH LEVEL MODULES SHOULD NOT DEPEND UPON LOW LEVEL MODULES. BOTH SHOULD DEPEND UPON ABSTRACTIONS.
>
> B. ABSTRACTIONS SHOULD NOT DEPEND UPON DETAILS. DETAILS SHOULD DEPEND UPON ABSTRACTIONS.
>
> -- Uncle Bob

Stated differently, the DIP states that high level policy should not depend upon low level details. This principle is easily achieved by placing an abstraction between the high level policy and low level details. This abstraction should kept together with the high level policy, not with the low level details.
Out in the wild, you often see how this is partly implemented. Remember how you used to put the repository interfaces next to the implementations?

-----
This is the end of the SOLID principles for this article, if you want to read more about solid, I suggest you read Agile Software Developement, Principles, patterns, and practices which is published by Prentice-Hall.

Stay tuned for the next part of this series about the principles of object oriented design.
