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