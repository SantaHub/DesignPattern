# Software Architecture

How software architecture is constructed at the highest level. The elements in the systems, functionality of each element and how each element is related.

## Kruchten’s 4+1 View Model

Logical view : Functionality and objects. UML Class diagram and state diagrams, allows visibility on objects required.
Process view : implementation of the functionality considering performance and scalability. Activity diagram and sequence diagram, makes it easier to understand flow.
development view : components used for implementation. Language, Libraries, databases schemas. Hirarchical software structure and project management.
physical view : physical components and deployment hardware requirements. Deployment diagram.

Scenario : use cases. Provides context for all the views.

## Component Diagram

To visualize interaction and relationship among pieces of a system. They show high level structured view. Component diagrams have ball connectors, which represents provided interface and socket connectors, which represet a required interface.

Assembly relationship : when a components required interface matches with the provided interface.

On architecturing, the system will have components ranging from classes to external libraries denoted in assembly relationship.

Useful early on the design process. It can be drawn to focus on systems and subsystems.

LucidChart : <https://www.lucidchart.com/pages/uml-component-diagram>

## Package Diagram

Package is to group elements and to provide a namespace for those elements.

Package diagram provide high-level grouping of a systems including data, classes or other packages. It makes it easy to see how a packaege contains related elements as well as how different packages depend on each other.

## Deployment diagram

Visualize deployment details of system, including more than code, libraries, installers and configuration files. Deployment diagrams deals with artifacts, including the executable, audio and mulitmedia assets.

There are two types of deployment diagram :

- specification-level diagram : general overview of deploymment
- instace level diagram : More detailed specifics

Nodes : deployment targets like linux OS
Manifestation : Realization of software component. Life class manifesting to player object during executation.

Lucid Chart : <https://www.lucidchart.com/pages/uml-deployment-diagram>

## Activity Diagram

