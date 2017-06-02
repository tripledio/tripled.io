---
layout: post
author: domenique
header-img: "img/levelsofabstraction.jpg"
disqus: true
---
Writing code is all about abstractions, they help us grasp the complexity
of the code by hiding low level details from high level concepts.
The key to readable code lies in grouping the right level of abstraction in the same unit of code.

Kent beck originally came up with the following guidelines in his book *Smalltalk best practice patterns[^1]*:
>Divide your program into methods that perform one identifiable task. Keep all of the operations in a method
at the same level of abstraction. This will naturally result in programs with many small methods, each a few lines long.

Later on this concept got coined by Neil Ford as SLAP: Single Level of Abstraction Principle in his excellent book *The Productive Programmer[^2]*,
afterwhich Robert C. Martin restated the principle in his *Clean Code[^3]* book:
>Mixing levels of abstraction within a function is always confusing.
Readers may not be able to tell whether a particular expression is an essential concept
or a detail. Worse, like broken windows, once details are mixed with essential concepts, more and more details tend to accrete within the function.

Kent Beck originally proposed the concept of composed methods. A composed method consists
of multiple calls to other private methods, each having a clear name to identify it's responsibility.
This technique results on smaller methods having only one level of abstraction and by consequence only one responsibility.
The following code sample illustrates what this would look like.
<script src="https://gist.github.com/domenique/a90553e06fc3c1bff41b297f4a37b24c.js"></script>
As you can see there are at least 2 levels of abstraction in this code. the `makeCoffee()` method exhibits
a higher level of abstraction then the other methods. It acts as an orchestration layer, enforcing policy on the other methods.

## Code smells
### Loop bodies
Often the body of a loop can be extracted resulting in a separate private method. Loops should ideally contain
a single statement (usually a method call). Sometimes this is not achievable without other drawbacks but certainly
large loop bodies can be considered a smell.
<script src="https://gist.github.com/domenique/2b5ff037de296cf6f7be6a127360c025.js"></script>
The example above is a factory responsible to convert our `Car` entity to a data transfer object.
Look carefully at the `create` method. First there is the loop which acts on the whole result set,
secondly there is the loop body which converts a single `Car` Entity to a `CarDto`. The body of the
loop could easily be extracted, avoiding mixing the level of abstraction.

### Abstractions and layering
Methods are not the only place where abstractions are at play. Layers inside our
application should also adhere to the same level of abstraction across the application.
In a typically layered application, we are supposed to find specific levels of abstraction
in each of the layers. Meaning that when you look at the application from the boundaries inwards,
our code should get more specific when passing through each layer. Failing to do so, results in code which is hard to read.
#### The application layer
A typically layered application consists of an application layer, or a service layer which acts as a facade
in front of the domain model, this layer contains use cases or command handlers. It contains high level
policy which can be understood by a business stakeholder by looking at the name of the class and its content.
This layer should not contain any business logic, it merely orchestrates the domain layer, as a result,
the code should be concise and easy to read.
#### The domain layer
The domain layer is a lower level of abstraction, it contains detailed business logic which is accessed from the application layer.
The code in this layer will be a lot more complex then the application layer. If you want more details about specific business rules,
how they relate to domain entities or aggregates then this is the right place to look. The domain layer will typically have different
levels of abstractions in its own. Aggregate root entities exhibit a higher level of abstraction then entities.
#### The infrastructure layer
The infrastructure layer consists of the lowest level of abstraction, it deals with the nitty-gritty details
such as database persistence, networking protocols and other details needed by the domain layer to persist
data or communicate with other systems.

## Footnotes
[^1]: *Smalltalk best practice patterns* by **Kent Beck**, isbn 9780132852098.
[^2]: *The productive programmer* by **Neil Ford**, isbn 9780596519780.
[^3]: *Clean code* by **Robert C. Martin**, isbn 9780136083238.