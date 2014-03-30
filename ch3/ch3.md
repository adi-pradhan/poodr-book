#Chapter 3: Managing Dependencies

Messages pass between objects in a real life application
Each message is initiated by an object to invoke some behavior

For any behavior an object either knows it personally , inherits it or knows another object that
knows it

Because well designed objects have a single responsibility their nature requires that they collaborate
to achieve tasks. This collaboration can create dependencies and if not managed carefully the dependencies
can strangle an application.

##Understanding Dependencies

An object depends on another object if when one is changed the other is forced to change in return

An object has a dependency when it knows
- The name of a class it calls
- The name of a message to call on that class
- The number of arguments to a message
- The order of arguments to a message

Some degree of dependency is inevitable but this is un-necessary. 

These dependencies couple classes.

##Coupling between Objects

When classes know more about each other they are coupled. The more couples they are the more they behave as a single entity

Coupling makes re-use difficult.

##Other Dependencies

One other kind of dependency occurs when an object knows about another who knows something. 
That is where many messages are chained together to reach behavior that leaves in different objects.

'knowing the name of a message you plan to send other than self' dependency

Another dependency is that of tests on code. Tests may be too tightly coupled with code and this causes tests to break
every time the code is refactored.  Tests thus begin to cost too much.

##Writing Loosely Coupled Code

Techniques to reduce dependencies by decoupling code:

###Inject Dependencies

The class of an object you wish to collaborate is not really important , it is the message you wish to send to it.

This is duck-typing. Objects do not care about the classes of objects they with to collaborate with.

You can make the dependency a parameter to the initialize. The class previously had explicit dependencies but through injection 
these dependencies are reduced to a single one. The class is now smarter because it knows less.

Always try to isolate dependencies if they cannot be removed.

###Isolate Instance Creation

###Isolate Vulnerable External Messages
You can wrap external messages in methods e.g.

def diameter
	wheel.diameter
end

###Remove Argument Order Dependencies
Use hashes for initialization arguments
This removes the dependency of argument order. 

Even if you don't have a choice i.e. you've included a library that enforces parameter order, create a wrapper class/module

Using a module lets you define a separate and distinct object to which you can send messages but also lets you 
convey the idea that you don't expect instances of this object.

If a object's sole purpose is to create instances of another class, it is known as a __factory__

Do __not__ allow external dependencies to permeate your code. 

##Managing Dependency Direction

###Reversing Dependencies

If classes were people, you would tell them to __depend on things that change often than you do__

###Recognizing Concretions and Abstractions

Unlike Java in Ruby there is no such thing as an abstract interface however you are actually creating an interface when you inject Wheel 
into Gear such that Gear depends on a duck that reponds to diameter. 

This interface is an abstraction of the idea that a certain category of things will have a diameter.

Ruby does not make you explicitly declare an abstraction but for design purposes it is good to imagine the virtual interface.

Any class that if changed will cause ripples in your application will be under enormous pressure to never change.


