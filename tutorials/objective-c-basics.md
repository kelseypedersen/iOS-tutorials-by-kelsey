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

### Views
Views can serve as containers for other views in addition to displaying information and handling user inputs. Views are arranged in a hierarchical structure called the view hierarchy, which defines the layout of views relative to other views. Within this hierarchy, views enclosed within views are called subviews and the parent view that encloses a view is called a superview. A view can have multiple subviews, but only one superview.

Top of the Hierarchy
- UIWindow class
- ContentView object
- subviews
- subviews
- etc.

For a content view and the subviews to be visible, the content view must be inserted into the window's view hierarchy. This is automatically configured when using storyboards.

An app launches, the application object (main.m) loads the storyboard, creates instances of the relevant view controller classes, unarchives the content view and subviews for each view controller and then adds the content view of the initial view controller into the window.

### Actions
A piece of code linked to an event that can occur in an app. When the event occurs, the code is executed. An action can accomplish anything from manipulating a piece of data to updating the interface. Actions are used to drive the flow of the app in response to user or system events.

An action is defined by creating and implementing a method with an IBAction return type and sender parameter.

```
- (IBAction)restoreDefaults:(id)sender;
```

The sender is necessary because it points to the object that is responsible for triggering the action. IBAction is a special keyword, like void, that indicates the method is an action.

### Outlets
A piece of code used to reference interface objects from source code. To create an outlet, C-drag from an object on the storyboard to a viewController file. This creates a property for the object in the viewController file, which lets you access and manipulate that object during runtime.

```
@property (weak, nonatomic) IBOutlet UITextField *textField;
```

### Navigation Controllers
Manages back and forth transitions between viewControllers, eg. navigating from email accounts to inbox to individial emails in the iOS Mail App. The set of viewControllers managed by a particular navigation controller is called the navigation stack. The navigation is last-in, first-out collection of custom viewController objects. This means the first item added to the stack with be the root viewController and is never popped off the stack. Other viewControllers are popped on and off the stack.

You do not need to do any manual work to pop on or off viewControllers, the back button does that for you. (Awesome!) But you do need to manually add viewControllers to the stack, which can be done via the storyboard.

### Segues - Transitioning Controllers
The transition between 2 viewControllers: the source and the destination.

1. Show: pushes new content on top of the current viewController stack. Where the content shows up depends on the layout of the viewControllers in the scene.
2. Show detail: pushes new content on top of the current viewController stack or replaces the content shown, depending on the layout of the viewControllers in the scene.
3. Present Modally: A modal segue is one viewController presenting another viewController modally, requiring a user to perform an action before returning to the presenting viewController. Isn't added to the navigation stack, child of presenting viewController. The presenting viewController is responsible for dismissing the modal viewController it created and presented.
4. Popover Presentation: The presented viewController is shown as a popover anchored to an existing view.
5. Custom: UIStoryboardSegue
6. Unwind: Moves backwards through one or more segues to return the user to an existing instance of a viewController. Used to implement reverse navigation.

Scenes can also be connected by relationships. For example, the relationship between the root viewController and the navigation viewController. This relationship represents the containment of the root viewController by the navigation viewController.
