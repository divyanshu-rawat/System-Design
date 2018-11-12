
This article is broken down into the following four sections:

* Ask clarification questions
* Use your background
* Tackle a problem systematically
* Keep your own notes

* How you would think about the problem space?
* How you think about bottlenecks?
* What you can do to remove these bottlenecks?


A good clarification question helps you achieve one, or more, of several things?

* Helps you narrow the scope of what you’re supposed to do
* Helps clarify what the user expectation of the system is
* Gives you direction about where to proceed
* Informs you of possible bottlenecks/problem areas

* What is the goal of the system?
* Who are the users of the system?
* What is the scale we’re working with?
* Is this a new/old system? How do we handle versioning?



My coffee-ordering service is a software as a service (SAAS). It offers an interface for various partners to plug into.

* It has an API, called addCoffeeForMerchant, that inserts coffee name, coffee price, and coffee ingredients.
* It has a GET API, called getCoffeesForMerchant, that returns a list of coffees for a given merchant ID.
* The merchant ID is a unique identifier (UUID) that is generated using some hashing mechanism, which can be further clarified with the customer.
* The software is optimized for read-only operations, because most of my customers create their menu once and read it multiple times throughout the day.
* It has a caching mechanism that uses Least-Recently-Used (LRU) eviction strategy, because if the menu item hasn’t been ordered in a while, my customer doesn’t care if it’s slightly slower in showing up on the menu.
* In case one of the data stores self-erupts, my coffee-ordering service will replicate data across different clusters across US west and US east coast because I am targeting the US market only for now.

Alternatively, any other coffee-ordering service that you can think of would be highly probable as well. It’s just a matter of what you’re optimizing for. I think these are very interesting problems, and it’s a great mental exercise to keep your mind engaged.

[READ MORE HERE](https://medium.freecodecamp.org/how-to-system-design-dda63ed27e26)
