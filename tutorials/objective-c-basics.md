## Objective C Basics

### Objects - Building Blocks
A way to package data with related behavior. An app is a innerconnected web of objects talking to each other, e.g. visual elements responding to user input and saving the data. There are many different types of objects used to build an app from the visual elements, like buttons, labels and table views to the data structures like strings and arrays. These are all objects.

### Classes - Blueprints for Objects
Describes behaviors and properties common to a particular type of object. Every instance of a class shares the same behaviors and properties. You can write your own classes or use predefined classes (e.g. arrays, strings, buttons, etc.).

You make an object by creating an instance of a class. You do this by allocating the object and initializing it with default values. When you allocate an object, you are setting enough memory aside for the object and setting the instance variables to zero.

Initialization sets the object's initial state -- it's instance variables and properties -- and returns the object. The purpose of initialization is to return a usable object. You need to allocate and initialize an object to be able to use it.

Class inheritance is a widely used object-oriented concept: the idea that a class inherits behaviors and properties from a parent class. The subclass (or child) can also define its own additional behavior and properties, which can override the behavior of the parent. This means, you can extend the behaviors of a class without duplicating its existing behavior. Woohoo!

### Messages - The Way Objects Communicate
Objects talk to one another by sending messages at runtime. In Objective-C, one object sends a message to another by calling a method on that object.

If you have an object someDog of class xyzDog, you can send it the sayWoof message like this:

```
[someDog sayWoof];
```

someDog is the receiver of the message. sayWoof is the name of the method to be called on the receiver. Aka, someDog will be sent the sayWoof message at runtime.

```
Current Execution Point
[someDog sayWoof]

@implementation xyzDog
- (void)sayWoof{
  NSLog(@"Woof! Woof!");
}

@end
```