# Software Architecture

How software architecture is constructed at the highest level. The elements in the systems, functionality of each element and how each element is related.

## UML Architecture Diagrams

Different UML diagrams and how each contribute to designing of the Architecture.

### Kruchten’s 4+1 View Model

Logical view : Functionality and objects. UML Class diagram and state diagrams, allows visibility on objects required.
Process view : implementation of the functionality considering performance and scalability. Activity diagram and sequence diagram, makes it easier to understand flow.
development view : components used for implementation. Language, Libraries, databases schemas. Hierarchical software structure and project management.
physical view : physical components and deployment hardware requirements. Deployment diagram.

Scenario : use cases. Provides context for all the views.

### Component Diagram

To visualize interaction and relationship among pieces of a system. They show high level structured view. Component diagrams have ball connectors, which represents provided interface and socket connectors, which represet a required interface.

Assembly relationship : when a components required interface matches with the provided interface.

On architecting, the system will have components ranging from classes to external libraries denoted in assembly relationship.

Useful early on the design process. It can be drawn to focus on systems and subsystems.

LucidChart : <https://www.lucidchart.com/pages/uml-component-diagram>

### Package Diagram

Package is to group elements and to provide a namespace for those elements.

Package diagram provide high-level grouping of a systems including data, classes or other packages. It makes it easy to see how a package contains related elements as well as how different packages depend on each other.

### Deployment diagram

Visualize deployment details of system, including more than code, libraries, installers and configuration files. Deployment diagrams deals with artifacts, including the executable, audio and multimedia assets.

There are two types of deployment diagram :

- specification-level diagram : general overview of deployment
- instance level diagram : More detailed specifics

Nodes : deployment targets like linux OS
Manifestation : Realization of software component. Life class manifesting to player object during executation.

Lucid Chart : <https://www.lucidchart.com/pages/uml-deployment-diagram>

## Activity Diagram

Designed to capture the flow of the system. It captures dynamic behavior and allows the mapping into alternative flows. 
Lucid Chart : <https://www.lucidchart.com/pages/uml-activity-diagram>

## Architectural Styles

## Language Based Systems

Each programming language have its own programming paradigm and has its own set of constructs, principles and design patterns.

OOPs :
    - Abstraction : simplifies a concept
    - Encapsulation : Bundle data and functions
    - Decomposition : Breaks whole into parts
    - Generalization : allows to factor out conceptual commonalities.

OO DP :
    - Creational Patterns : Guide the creation of object
    - Structural Patterns : relationship between classes and subclasses
    - Behavioral Patterns  : Objects work individually or as a group to perform functionalities

### Abstract and Object Oriented Design

OO Architecture is focused on data, how its modeled and grouped. Encapsulation restricts access and use of it.
Evaluating the data types used, the system can be broken down into abstract data types. Classes help to group data and related methods together.

Access Specifiers and methods : allow inter object communication
Inheritance : allow extensions on abstract types.

### Procedural Design

Main Program and subroutine architectural style is used in the procedural programming paradigm. Idle for computation centered systems.
The subroutine is also termed as routine, procedure and functions.
The main program would call routine and they in-turn calls subroutines.

## Repository based system

### Database

Data centric architecture is preferred when in need to share vast amount of data between systems.
It is also scalable and can be easily integrated with multiple data accessors.
The qualities of data-centric architecture are :
    - Data integrity
    - Data persistence

## Layer Systems

Very common architecture.

The architectures can sometime be designed in layers which one layer talking only to its adjacent layer.
These systems provide :
    - security and reliability of the core layer
    - Design is loosely coupled and follows principle of least knowledge.
The overhead of layering should be balanced against separation of concerns gained.

### Client server n-tier

Tiers refer to component that are typically on different machines. 3 tier and 4 tier architecture are common.
The adjacent tiers will have client/server relationship. The communication can be asynchronous or synchronous.

Difficulties are in tier communication protocols. and multi point of failure servers.

Advantages are :
    - scalable. The servers can handle large amount of requests.
    - Data reside in on machine and is available to all machines in the network.
    - allows client machine to be powerless thus providing power as a service.
    - Supports separation of concerns. more tiers are added to further loosen the coupling.

## Interpreter based system

These systems are portable as they can work off any platform. Eg: Java
Interpreters can be slow. It uses line-by-line translation and execute strategy.

### State Transitions systems

A state system is designed to execute tasks in the most efficient way. They would be assigned a large amount of processes.
State systems allows to find deadlocks. Eg OS

## Data-flow system

### Pipe and filter architecture style

Filter : perform transformation on data input.
Pipes : Serve as connectors for the stream of data.

Advantages of pipe and filter architecture: 
    - Loose and flexible coupling of components.
    - filters are black boxes
    - reusability. Used in different application

Disadvantages :
    - Reduced performance due to overhead in filters.
    - If a filter gets takes too long to process it will keep other filter in waiting state
    - Cant be used for interactive applications which needs rapid response.

## Implicit invocation Systems

### Event -based architectural style

Events are both indicators of change and triggers to functions. Event generators and event consumers.

Function types:
    - Asynchronous : event consumers could be running simultaneously on shared global data. Effecficient, but can cause race condition.
    - Synchronous : 

Race condition : behavior of a function depend on the time and order of data. A condition in which data might not be updated correctly.
Semaphore : A boolean value to indicate availability state of shared data. 
Event Bus : All stream of events mapped to consumers. When an event is triggered its added to the bus and executed based on asynchronous or synchronous.

### Publish Subscribe

A subscribe register to publishers through a call-back.
The publisher maintain a list of subscribers and communicate to them through procedure calls.

This works when the list of subscribers are small. In Large scale application, the architecture is adapted by making the system loosely coupled components. A connector is introduced to distribute and possibly filter messages to the subscribers. The connector coulbe be event bus or network procotovol. This relieves the work of publisher, also allows complex filtering of messages.

Eg : RSS feed, mailing list.

## Process Control Systems

They are important in efficient and safe operation. 

### Feedback loop

Feedback loops have 4 basic component :
    - sensor
    - controller
    - actuator
    - process
Feedback loops are designed for closed system. Other variants of feedback loop for open system is Feedforward control, they are designed to control process in series.

## Architecture in Practice

## Architectural Tradeoffs

### Quality Attributes

Developer Perspective :
Properties used to gauge system design,run time performance and usability.
    Maintainability : How easy the system can undergo change. Ease of repair and minor change.
    Flexibility : Changeability over requirements. Ease of expanding product.
    Reusability : Portability of system functionalities. Eg: micro-services
    Testability : Ability to allow feature testing.
    Conceptual Integrity : Consistency across system. Naming convention, design followed.

User Perspective :
    Availability : High SLA
    Interoperability : information exchange and data handling. Protocols, Data format.
    Security : Authorized accesses.
    Data integrity : Data access
    Performance : Throughput and latency
    Usability : UX

How to design high quality system?
    - Architecture design : Go for the simplest solution that satisfy all requirements. Once decided shouldn't be altered.
    - Documentation : The Arch design should be documented
    - Methodical : Set rules, guidelines, design process and structure.
    - Involve Tech Lead for design to implementation, stakeholders to confirm requirements.

Structural rules :
    - Well defined subsystems with responsibilities and design principles
    - Consistent implementation of functions. All subsystems should follow similar principles.
    - Rules on resource on usage.

In summary, when selecting the appropriate architecture, involve all stakeholders in the design, adopt good documentation practices, and set rules for design and implementation.
A well-designed system considers quality attributes from a developer’s perspective, which includes maintainability, reusability, flexibility, modifiability, testability, and conceptual integrity; the system should also consider attributes from a user’s perspective, which includes availability, interoperability, security, performance, and usability.

### Analyzing and Evaluating Architecture

ATAM developed by Carnegie Mellon University, allows outsiders to evaluate systems they are not part of.
There are 3 main groups :
    - Evaluation team
    - Project decision makers
    - architectural stakeholders
    
The Evaluation team has 3 groups :
    - Designers :
        - Responsible for architectural design
        - Follow iterative hypothesis driven design.
        - Analyzing requirements, Creating a design, reviewing the design
    - Peers :
        - Other software teams
        - allows different view points
    - Outsiders :
        - They should be experienced in architectural evaluation.

ATAM Process :
    - Present the ATAM : Evaluation team present ATAM process, including context evaluation, expectations, procedures, outputs and concerns.
    - Present business drivers : Project decision makers present business problem and goals fro the system. Also features, requirements, constrains and scope.
    - Present the architecture : Current architecture is presented with constrains, time, cost, difficulty and quality.

    - Identify architectural approach : first analysis activity, involves examining the architectural patterns used, involving all stakeholder's queries.
    - Create a quality attribute tree : Requirement for each quality attribute is detailed. Gain insight on the system and quality ASR (Architecturally significant requirement) by working with project decision makers to refine this utility tree.
    - Analyze the architectural approaches : From the utility tree, the ASR is analyzed to how well the current architecture meet them. This allows to identify risk and non-risk scenarios, sensitivity points and trade-offs.
    - Brainstorm and prioritize scenarios : Each team would create their own prioritized utility tree which is merged together.
    - Re-analyze architectural approach : The architectural approach is reanalyzed to reduce the difference between architectural utility tree and requirements utility tree.
    - Present the result : The result contains :
        - risk scenarios : grouped together as risk themes. This helps to identify affected user base.
        - All risk and non risk scenarios
        - sensitivity points
        - tradeoffs
        - risk themes

## Product Architecture

Conway's Law : The states of a software system will tend to take form that in congruous to the organization that produced it. Open sourced softwares are more loosely couples than in house build softwares. Allowing teams to be modular helps create modular systems.

### Produce Line and Product Families

Product line or families harness code re-use.
Produce line are groups of products that share same OS, which allow a great deal of code re-use. 

Product Line architectural consideration :
    - Commonalities : features same throughout all products
    - Variations : Features that vary between products.
    - product specification : features that are unique product.

Development Teams are divided as :
    - Domain engineering : development of commonalities and variations. They focus on reference architecture which all products in the line use.
    - Application engineering : development of product, product specific features.

To realize variation on the system :
    - Adaptation technique : Component has only one implementation but supplies interfaces, configuration files or method overriding to adapt for a problem.
    - Replacement technique : There would be a gap in the system and developer supply on component to suit it for the problem.
    - Extension technique : Common interface provided, onto which different components could be attached. Eg : extension, add-ons or plugins.
