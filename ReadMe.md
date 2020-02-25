# Design Patterns. 
Head First Series 12 Design Patterns. ISBN : 9788173664663

Design Patterns: Elements of Reusable Object-Oriented Software, 23 Design Patterns.

[Coursera Design Pattern University of Alberta](https://www.coursera.org/learn/design-patterns)

    The 23 Design pattern book was written by "Gang of four", They have categorized the patterns into 3 categorize to structure them in their books, some of the patterns span all categorizes and without a clear cut. The categorize are "Creational Pattern, Structural Pattern, Behavioural Pattern"

## OO Basics
    - Abstraction
    - Encapsulation
    - Polymorphism
    - Inheritance

## OO Principles
    - Encapsulate what varies
    - Favor composition over inheritance
    - Program to interfaces, not implementations
    - Strive for loosely coupled designs between objects that interact

## SOLID Principle
    - Single Responsibility
    - Open for extension, Closed for modification
    - Liskov substitution principle
    - Interface segregation principle
    - Dependency inversion principle

## The gang of Four
    Book : Design Patter : Elements of Reusable Object oriented Software
    Authors : Erich Gamma, John Vlissides, Richard Helm, Ralph Johnson
    They have identified and classified Design patterns into 3. Some patterns have blended boundaries through multiple patterns

### Pattern Language 
    Also known as implementation language. Each specific are has its own pattern langauge, such as in accounting, the double entry book keeping vs the game theories in game development. The Pattern languages are specific some areas and needed to be learned to solve problems in that field.

## Creational Patten
---
    Deals with creation and cloning new object.
    In java, the objects are desided at compile time. 
    In javascrript, the objects can be cloned and exteneded during run time.

### Singleton Pattern
    - Class can have only one object.
    - Use a object check to see if an instance is already created.
    Pros :
        - Restrict unwanted object creation in large projects with multiple developers
    Cons :
        - Have thread wait issues during multithreaded application
    The multithread issue can be solved by using synchronized methods. 
    Even better, use double checking to avoid the overhead of synchronized method, instead use a synchronized block for just assigning the object. Checkout the article in [geeksforgeeks](https://www.geeksforgeeks.org/java-singleton-design-pattern-practices-examples/).

### Factory Pattern
    - A conditional statement decides which object has to be returned.
    - Since the factory method deals with the object creation, the other components of the program can deal with the functionalily, but should be in a generalized way

## Structural Pattern
---
    Deals with how the objects are connected to meet a specific design goal. DP of Decomposition and generalization.

### Facade Pattern
    Provide client simple interface for complex backend.
    - All service classes can be wrapped using a common Interface
    - A Controller is used as a Facade which instantiate services using the Interface type.
    - Used when the Program has multiple similar type of service. Ex : Bank account types.
    - DP used : encapsulation, information hiding and Seperation of concern
    Example : Restuarant Menu, Delivery Services, Bank Services.

### Adapter Pattern
    Provides a transilation on one service for another
    - Translates the messages from adaptee to client and vice versa.
    - Used when to incompactable service need to work together
    - Neither of the service modification to be directly compactable is possible 
    Example: An XML based service talking to a Json REST Service

### Proxy Pattern
    Simplified or light-weight object inplace of the original Object
    - The real object may resource intensive or have sensitive data
    - Proxy classes implements same interface as real objects.
    - Proxy Classes can be a validator for the real object class.
    Example: Personal Assistant.

### Decorator Pattern
    Uses aggregation to build up stack of object at run time
    - Decorator acts as the implementor
    - Decorator will contain the object its decorated on inside as a variable.
    - Lets say we have make a dark Roast
        - Create an interface of Beverage.
            - Dark Roast implements Beverage
            - Decorators Interface implements Beverage
                - cream whip class with Decorator interface
                - choco chips class with Decorator interface
            - Set the Decorator classes to call cost fn of the object it is decorating. 
            - like def cost() : myCost+super.cost()
            - The Dark Roast would then stack the decorators
                - DR =new DarkRoast(); DR = new Cream(DR); DR = new Choco(cream) 
                - dr.cost(); would call cost from choco to DarkRoast.

## Behavioural Pattern
---
    How the each object in the design work together to achieve same goal.   

### Stratergy Pattern
    - use interfaces to build Object Types. 
    - Assign an implementation to the object as per stratergy.
    - Example : Character Interface. King, Queen, Knight implementations of it.

### Observer Pattern
    - Publisher, Listener/Observer 
    - Can use the Java build in Observer interface
    - Extends Observable. java.util.Observable
        - setChanged()
        - notifyObservers()
    - One to many relationship and loosely coupled. Java util Observable voids these principles by being a class. 

## Template Method Pattern
    Should have 3 components
    - 'final' Template method that has several steps (public final void driveToDestination() )
    - 'abstract' methods defined by the subclasses (protected abstract void accelerate(), steer(), and brake())
    - May have a 'private' common method. (private void reachDestination() )
### State Pattern
    Uses a state interface.
    - Each state would do its function and change the 'current state' to the next state.
    Example : states of a vending machine

### Command Pattern
    Makes a command object each time an event occurs. This helps to keep the events independent of the user interface. Each time a button is clicked a command object of the type is created and executed.
    - Each command has a execute(), unexecute() and isReversable() fns

### Mediator Pattern
    When multiple objects have to corrdinate with each other, instead to pair collaboration, they all talk to a mediator which then using its logic request tasks to other recepient objects
    Colleagues : Objects associated with the mediator
    - Mediator allow loose coupling between components
    - Took much configuration to the mediator could make the class large.