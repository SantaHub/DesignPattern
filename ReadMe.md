# Design Patterns. 
    Head First Series 12 Design Patterns. ISBN : 9788173664663
    Design Patterns: Elements of Reusable Object-Oriented Software, 23 Design Patterns.

    The 23 Design pattern book was written by "Gang of four", They have categorized the patterns into 3 categorize to structure them in their books, some of the patterns span all categorizes and without a clear cut. The categorize are "Creational Pattern, Structural Pattern, Behavioural Pattern"

## OO Basics
    - Abstraction
    - Encapsulation
    - Polymorphism
    - Inheritance

## OO Principles
    - Encapsulate what varries
    - Favor composition over inheritance
    - Program to interfaces, not implementations
    - Strive for loosely coupled designs between objects that interact

## SOLID Principle
    - Single Responsibility
    - Open for extension, Closed for modification
    - Liskov substitution principle
    - Interface segregation principle
    - Dependency inversion principle


## Creational Patten
    Deals with creation and cloning new object.

### Singleton Pattern
    - Class can have only one object.
    - Use a object check to see if an instance is already created.

### Factory Pattern
    - A conditional statement decides which object has to be returned.
    - Since the factory method deals with the object creation, the other components of the program can deal with the functionalily, but should be in a generalized way

## Structural Pattern
    Deals with how the objects are connected to meet a specific design goal. DP of Decomposition and generalization.

### Facade Pattern


## Behavioural Pattern
    How the each object in the design work together to achieve same goal.   

## Stratergy Pattern
    - use interfaces to build Object Types. 
    - Assign an implementation to the object as per stratergy.
    - Example : Character Interface. King, Queen, Knight implementations of it.

## Observer Pattern
    - Publisher, Listener/Observer 
    - Can use the Java build in Observer interface
    - Extends Observable. java.util.Observable
        - setChanged()
        - notifyObservers()
    - One to many relationship and loosely coupled. Java util Observable voids these principles by being a class. 

## Decorator Pattern
    - Wraps an object over another. Decorator will contain the object its decorated on inside as a variable.
    - Lets say we have make a dark Roast
        - Create an interface of Beverage.
            - Dark Roast implements Beverage
            - Create an interface Decorators implementing Beverage
                - Create cream whip class with Decorator interface
                - Create choco chips class with Decorator interface
            - Set the Decorator classes to call cost fn of the object it is decorating. like def cost() : myCost+decor.cost()



## Command Pattern
    - 