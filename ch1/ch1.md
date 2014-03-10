#Object-Oriented Design

##Procedural vs Object Oriented

The world may be procedural or object-oriented. Objects are 'things' you interact with. They have behavior and state

Interaction between objects comes naturally. 

OOD requires modelling the world as a series of messages that pass between objects

Change in software is inevitable. Therefore applications that are easy to change are more pleasant to work with.

OOP: parts interact to produce the behavior of the whole.

OOD is about managing dependencies. It is a set of coding techniques that arrange dependencies wuch that objects can tolerate change. 

Objects that know too much have many expectations about the world they live in. The expectactions constrain them and make them less susceptible to change. 

##Design Principles

3 known techniques are SOLID, DRY and Law of Demeter

SOLID
- Single Responsibility
- Open Closed
- Liskov Substitution
- Interface Segregation
- Dependency Inversion

DRY
- Don't Repeat Yourself

Law of Demeter

Design Patterns are elegant known solutions to specific common and known problems. 

Design itself is a process of progressive discovery. Therefore Agile is a great way to design as you are constantly forced to look for feedback.

Agile vs BUFD/BDUF - Agile is better because you simply cannot known everything prior to start of the design phase.

BUFD provides a feeling of control that would otherwise be lacking. 

Note that Agile does not mean "do not do any design at all". BUFD is about having a complete specification. Agile is about designing while understanding the requirements will be dynamic. 

##Brief Intro to OOP

OO apps are made up of objects and the messages that pass in between them.

Procedural Languages have a chasm between data and behavior i.e. data is one thing and behavior is quite another. Data gets packaged and sent to behavior which does whatever it wants with it. 

In OOP data and behavior and combined into a single thing, the Object. Objects have behavior and may contain data which they control access to. Object may invoke each other's behavior by sending each other messages. Methods are invoked in response to messages. 

Each object encapsulates or hides its data from the world. 

A Class provides a blueprint for the construction of similar objects. Classes define:
- methods (definitions of behavior)
- Attributes (definitions of variables)

Classes can be used to instantiate new instances of the object they are blueprinting. Each newly instantiated object implements the same methods and uses the same attribute names but contains its own data. 

Knowledge of an object's type lets you have expectations about the messages to which it responds. 

OOP is a little more interesting too e.g. the String class is itself an object. It is an instance of the **Class** class. Every class object is an instance of the Class class i.e. the classes are objects in themselves. The String class manufactures new string the Class class manufactures new classes. 

end of chapter 1

