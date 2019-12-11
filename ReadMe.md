# Design Patterns. Head First Series
    Book on 12 Design Patterns. ISBN : 9788173664663

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

## Factory Pattern
    - A conditional statement decides which object has to be returned.

## Singleton Pattern
    - Class can have only one object.
    - Use a object check to see if an instance is already created.

## Command Pattern
    - 