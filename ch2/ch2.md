#Chapter 2 

The foundation of an OO system is the message but the most visibel organizational structure is the class

Messages are really at the core of design. 

This chapter however deals with classes

- What are the classes ?
- How many should you have ?
- What behavior will they implement ?
- How much do they know about other classes ? 
- How much of themselves should be exposed ? 


The goal is to model the application using classes such that it does what its supposed to do right now AND make it easy to refactor so its easy to change later

The hard part is making it easy to change


##Grouping Methods in Classes

methods are defined in classes. Classes define the virtual world and constrain the imagination of everyone downsteam.

##Easy to Change Code
- Transparent: consequences of change should be obvious
- Reasonable: cost of any change should be proportional to the benefits
- Usable: 
- Exemplary: 

**T**ransparent **R**eadable, **Us**eable and **E**xemplary (TRUE)

To be **TRUE** a class must have a __Single Responsibility__
Meaning it should do the smallest possible useful thing.


Applications that are easy to change have classes that are easy to reuse

A class that has more than one responsibility is difficult to reuse

__Duplication is never a good idea__ as it leads to additional maintenance

##Determining if a class has a single repsonsibility

When everything in a class is related to its central purpose the class is said to be highly __cohesive__

###Data Access

Never access data directly. Always use __attr_reader__  which creates

def test
	@test
end

Always try to hide data from yourself. This will prevent tech debt by unexpected changes. Send messages instead of accessing data.

__Knowing the structure of data__ is even worse as it makes the class tightly coupled . 

If the structure of data e.g. an array with known values as indexes creates leaky references throughout the code. These references escape encapsulation.

If the structure changes then the code must change.

Direct references to complex structures obscure what the data really is.

You can use a Struct in ruby to wrap a structure and therefore use messages instead of array indices. That way the caller has no knowledge of the internal structure of the 
dependency

A __Struct__ is a convenient way to bundle a number of attributes together using accessor methods without having to write an explicit class.

###Methods

__Methods__ like classes should also have a single responsibility => makes them easy to change and easy to reuse.

Ask the methods questions about what they do and describe their responsibilities in one sentence. Refactor and if needed have methods call other methods. But ensure
that each method has a single responsibility.

Methods that have a single responsibility have the following benefit
- expose previously hidden qualities
- avoid the need for comments
- encourage reuse
- are easy to move to another class


##Isolate extra responsibility in classes

If circumstances allow you to create separate classes then you should create one. Structs may be morphed into classes.
"""
Wheel = Struct.new(:rim,:tire) do 
	def diameter
		rim + ( tire*2)
	end
end
"""

for example above may reside in your class Gear. But it is obvious that Wheel may exist independently of Gear.

