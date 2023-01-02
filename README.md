# Architectural pattern: ports and adapters (or also hexgonal architecture)
This repository is an example of a possible way to structure Golang projects using the hexagonal architecture pattern and thinking about some software design patterns like *Inversion of Control (IoC)* and *Dependency Injection (DI)*, as well as some design principles such as *Interface Segregation Principle (ISP)* and *Dependency Inversion Principle (DIP)*

### Domain
The main activity area (domain) of this project is to provide a REST API that works as a recipe finder.
  
### Hexagonal architecture
##### Key principles
- Everything depends on the Business Logic, the Business Logic does not depend on anything
- We isolate the boundaries by using Ports and Adapters
- The business is agnostic to the technologies and tools
- The business is protected from the outside

##### Concepts
- **Left side (or user side)**<br>This is the side through which the user or external programs will interact with the application. It contains the code that allows these interactions. Typically, your user interface code, your HTTP routes for an API, your JSON serializations to programs that consume your application are here.
This is the side where we find the actors who drive the Business Logic (primary adapters)
- **Center (business logic)**<br>Contains the business entities, rules, process and user cases 
- **Right side (or server side)**<br>This is where we’ll find what your application needs, what it drives to work. It contains essential infrastructure details such as the code that interacts with your database, makes calls to the file system, or code that handles HTTP calls to other applications on which you depend for example.
This is the side where we find the actors who are managed by the Business Logic (secondary adapters)
- **Port**<br>Defines the “how to communicates with business logic”
- **Adapter**<br>An adapter is responsible for communicating with the outside world with the business logic through ports defined by the business logic.
  - **Primary or driving adapter**<br>(Who drive the Business Logic)
  - **Secondary or drive adapter**<br>(Are managed by the Business Logic)
- **Materialization**<br>It is not an official term, but by this I mean the implementations of the primary ports that will be used for the primary adapters.

### DDD

##### Concepts
- **Business domain (or domain)**<br>A *business domain* defines the company's main area of activity
- **Subdomain**<br>A *subdomain* is a fine-grained area of business activity
  - **Core**<br>A core subdomain is a what a company does differently from its competitors.
  - **Generic**<br>A generic subdomains are the business activities that all companies are performing in the same way
  - **Supporting**<br>A support subdomain supports the company's business


<hr>

### 🧠 References
[Hexagonal architecture](https://alistair.cockburn.us/hexagonal-architecture/)

[Hexagonal Architecture: three principles and an implementation example - OCTO Talks!](https://blog.octo.com/hexagonal-architecture-three-principles-and-an-implementation-example/)

[Dependency inversion principle](https://en.wikipedia.org/wiki/Dependency_inversion_principle)

[Dependency injection](https://en.wikipedia.org/wiki/Dependency_injection)