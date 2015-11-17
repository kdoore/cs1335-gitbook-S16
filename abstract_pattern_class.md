# Abstract Pattern Class

Because we want to have multiple patterns for our drawing application, we need to have a base-class that will allow us to refer to a variety of different pattern class objects to keep track of the current active brush pattern.  Since the code for most patterns is simply a display method, without any instance variables, and because the concept of a default pattern doesn't really make sense, each of these patterns will be based on a unique class.  The only real shared features of these Pattern classes is that they will all implement a display method.  Therefore, we can create a base class:  ``Pattern `` that we define as an ``abstract class``

```
abstract