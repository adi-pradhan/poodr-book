#Designing Flexible Interfaces

An OO application is more than just classes. It is made up of classes but defined by Messages.

Classes control whats in cvs but messages reflect the living, animated application

Design therefore must be concerned with the messages that pass between objects. This deals with
- what objects know
- who they know
- how the objects talk to each other.

The conversation between objects takes place using their interfaces.

##Understanding Interfaces

When the message patterns between object are visibly constrained, there is an agreement about which 
messages may pass between objects. The exposed methods that an object expects others to use
are called the class's __public interface__

Classes implement methods, some of these methods are intended to be used by others and these methods
make up it's public interface.

An alternative kind of interface is one that spans classes. Interface represents a set of messages where
the messages themselves define the interface. The interface defines a virtual class i.e. and class that 
implements the required methods can act like the interface kind of thing.

The second kind above is defined as duck typing ( a concept broader than a class and defined by messages)

##Designing Interfaces

A class exists to fulfill a single responsibility but it implements many methods. These methods vary in scale and granularity. 

There may be broad general methods and tiny utility methods. Some should be public others deal with internal implementation 
and should be private.

Public Interface
- reveal the primary responsibility
- expect to be invoked by others
- will not change on a whim
- Are safe for others to depend on 
- Are thoroughly documented in tests.

Private Interface
- Handle implementation details
- Are not expected to be sent by other objects.
- Can change for any reason
- Unsafe for others to depend on 
- May not even be references in tests.

##Responsibilities, Dependencies and Interfaces

If you think of a class as having a single purpose then the things it does allows it to fulfill its purpose.

There is correspondence between the statements you make about these more specific responsibilities and the classes' pubic methods.

Public methods such read like a description of responsibilities. The public interface is a contract that articulates the responsibilities of your class.

The public parts of a class are stable. The private parts are changeable. 

##Finding the public interface

pg. 63