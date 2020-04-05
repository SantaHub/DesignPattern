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

The goal of OO design is to :
    - help system be stable by closing classes for change
    - allow system extension through use of inheritance.

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

### Open/Closed Principle

- Classes should  be open for extension but closed for change.
  - Class extension can be achieved through inheritance or polymorphism.
    - final keyword is used to stop class extension through inheritance, either on a class or on method.
  - Extension through polymorphism can be achieved through Abstract Class or interface
    - Abstract class is used when a same set of attribute has to be used in multiple ways. Eg: sort and search.
    - We cannot set common attributes in interface.

### Dependency inversion

- Interface and abstract classes are considered high level resources while a concrete class is consider a low level resource.
- High level module should depend on high level generalizations and not on low level details.
- The client classes would be making reference to interface rather than into the concrete class.
- The method calls should be indirect unlike in procedural languages, OOD allows indirect class to methods through generalization and objects assigned.

### Composing Object Principle

- Composing Principle has come in to solve the problem in inheritance, the problem is that, a subclass would be able to access all the attributes and properties of its super classes with wide range of access specifiers.
- Composing achieve code reuse through aggregation rather than inheritance.
  - 2 DP using it are Decorator DP and Composite DP.
  - A concrete class delegates some responsiblities to other concrete class, thus offering less coupling.
  - Composing allow behavior changes during run time, while in inhertance is defined at compile time.
- Composing's disadvantage is that it cannot inherit similar code. The trade off has to decided at the design time.

### Interface Segregation Principle

- Developers should code to interface instead of concrete class.
- Interfaces should be segregated into part to tackle larger problems.
  - When designing a cashier system, it should have two interfaces, iCasher and iHumanWorker.
    - A human cashier should inhert both interfaces while a teller machine has to inhert only iCasher.
    - This allows the classes to has definite methods concerning to their specific type.

### Principle of Least Knowledge or law of demeter

- Classes should know about and interact with as few other classes as possible.
- A class should not call 2nd degree methods. Eg: car.engine.start(). It should be car.start() and car should take care of engine start.
- Another violation is when we are invoking methods of a returned object of unknown type. There are rules to define unkown.
  - A Returned object is known when Object is same type as :
    - declared in method parameter
    - declared and instantiated locally
    - declared instance variable of class that encapsulate the method.

---

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

    - Will have a subject class to allow new observers, remove current observers, notify observers.
    -

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

## Code Smell

- Too much or too little comments
- Large classes : poor seperation of class
- Large Methods
- DRY, duplicate code
- Data Clumps : Use objects instead of recurring sets of attributes. Eg: instead of int x, int y, int z use Coordinates xyz;
  - Be smart to use some other methods than just getter and setters.
- shortgun surgery : Sometimes to make a change we have to modify multiple places
- Feature Envy : If two classes are talking too much, they should be combined.
- Inappropriate intimacy : cyclic method call between two classes. Unavoidable in state DP.
- Message Chains : Should not call a method of an object thats retured. Its also violating law of demeter.
- Primitive Obsession : Too much primitive datatype.
- Switch statements : If used to check object type, migrate to polymorphism.
- Speculative Generality : Written for future. Should follow Just in time design based on Agile method.
- Refused Bequest : inheriting things thats not needed.
