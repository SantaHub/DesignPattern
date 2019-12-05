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
    - 