
##Explaining software
####.. to your grandma
Software development is hard. It's a complex undertaking with lots of people, there is always more to learn, making it hard to keep up. And it's also hard to explain to non technical people what we are doing and why it is taking so long :)

Corollary with the [Iceberg secret](https://www.joelonsoftware.com/2002/02/13/the-iceberg-secret-revealed/) [^n] non-technical people don't see all the complexity that lies beneath a pretty UI. This makes explaining the importance of a proper architecture or the maintainability of the software not easy. In this post i will try to arm ourselves with another software metaphor that hopefully can be used to illustrate some important software concepts to our grandma.

####The restaurant metaphore

In this post i will use a restaurant as my metaphor for software development. Because in a lot of ways, software development is kind of like owning a restaurant. But instead of ordering food, customer are ordering features. The software developers are the ones in the kitchen doing the cooking.

##Quick and dirty

In your average IT-workweek the sentence _"quick and dirty"_ is thrown around all too often. We are often told, or do it from our own volition, to do things _"quick and dirty"_. It doesn't have to be pretty, we need it fast, we need it now. There are always deadlines, always a sprint to complete, always someone or something breathing down our neck. Time pressure is always a given. And if it works, who cares what the code looks like. Besides a couple of idealistic geeks?

While of course we would all prefer to do something "quick and clean", that is a phrase you never hear. In fact we hear the phrase _"quick and dirty"_ so often that we think that the two are inseparable. That it is somehow impossible to do something quick without creating a mess. 

Now when it's lunch time in a busy restaurant, the kitchen is also in a mess while they are preparing food. But all the while there is someone in charge of cleaning up, doing the dishes, putting everything back in its _proper place_  You don't want the cooks waisting time doing the dishes or looking for their knifes, their casserole, their ingredients... while they should be serving the next customer. You want the cooks to have everything they need near by and at the ready. So that the kitchen team can prepare the food like a well oiled machine. For that you are more then willing to pay for the extra pair of hands that don't cook themself but hhelp keeping the kitche

##It works

The resulting software of the _"quick and dirty"_ approach is often accompanied with the statement: _"But it works!"_. To me this is often a red flag. As Uncle Bob stated in his classic book [Clean Code](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) [^n]: __"it is not enough for code to work"__. When something is _finished_ we expect it to work. This is the minimum requirement. But there are others...

The keyword in the _"quick and dirty"_ phrase is the word __and__. It signals that in order to do it _quick_ something else has been sacrificed which made the result _dirty_. Otherwise it would just be _"quick"_. No harm done. 

When something has been sacrificed to obtain speed it depends on the context wether or not this is a bad thing. We need to know what the expected attributes of the delivered solution are before we throw away some of them. Unfortunately that is a consideration that is seldom made. Speed is king, neglecting what was sacrificed to obtain it. 

Ideally we want to deliver the requested software with all its  required attributes (scalability, robustness, high performance, extensibility) as fast as possible.  



### The unwritten requirements

The feature will have, next to its functional requirements, also some additional attributes depending on the kind of software we are developing. Just like a different types of restaurants there are different kinds of software products. 

##The customer

In any given field, a customer usually want everything as fast as possible for the best price possible. All the while still expecting the product do have his desired attributes. 

To clarify what i mean with attributes let me jump right into my restaurant metaphor. Suppose i want to go to a restaurant to order food. When i go to a fast food restaurant i expect the service to be good and to receive my food faster than in a star restaurant. I do have different expectations on the quality of the food, the setting, the price... But no matter in which restaurant i eat, i always expect the food to be eatable. The eatable attribute can in no way be sacrificed for the quick attribute. If i get my food within seconds but if it is not eatable, i have paid for something without any value to me. The eatable attribute of my food is on the same level as the working attribute in software. If my software doesn't work, it's useless. No matter how fast i got it. The fact that i got my food very fast is unimportant. Simply because it is not food if i can not eat it. Or risk food poisoning. The same goes of course for my new feature. If it is delivered, but it does not work. Well then it simply isn't delivered. The fact that a feature should work hopefully resides in every developers [definition of done](https://www.agilealliance.org/glossary/definition-of-done/)

On the other hand if i have to wait for a long time before i receive my food i will not like it if i'm expecting fast food. But if the food is good then at then will soften the bad experience somewhat. If the food is late and cold, i'll ask my money back.

So it is our job to try to give the customer all the desired attributes. Dependeing on the context we can sacrifice some attributes for speed. Others we can not. Unfortunately the ones we can not sacrifice are often not specified explictly. We all understand that no matter what the food should be eatable. So deliverd software should always work. That should be a given. But it is not enough...


##The restaurant

//Snipets

One of my favourites blog posts is [The Tortoise and the Hare](http://www.artima.com/weblogs/viewpost.jsp?thread=51769) [^n] from Uncle Bob. In the blogpost he briefly uses a tractor pull as a metaphor. In [Clean Code: Episode 1](https://cleancoders.com/episode/clean-code-episode-1/show) he uses a sushi chef. 

//TODO

Structure vs behaviour episode 39 defects
The behavious is producing food. The structure is doing the dishes, cleaning up he kitchen so that you can continue to cook fast and dont poison anyone. You can postpone doing the dishes for a deadline. But not to long. Don't go home before doing the dishes. Dont let the dirty dishes start to smell.

+ home cooking
+ fast food
+ bigger restaurant
+ huge catering
+ Nobody remembers the speed, everyone remembers the mess
+ Attribute driven
+ poisonous food
+ serve more then one meal
+ send meals back since no good => nog bugs/ errors
+ go quick and well => practice , skilled professional. take time to learn. move potatoes, learn your ide
+ [Where is the foreman](https://8thlight.com/blog/uncle-bob/2014/02/21/WhereIsTheForeman.html)[^n]
+ [the land that scrum forgot](https://www.scrumalliance.org/community/articles/2010/december/the-land-that-scrum-forgot) [^n]

----------
*Guido Dechamps*

**Footnotes**
[^n]: [The iceberg secret] 
[^n]: [Clean Code] 
[^n]: [The Tortoise and the Hare]
[^n]: [Where is the foreman?]
[^n]: [The land that scrum forgot]