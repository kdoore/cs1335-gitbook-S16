# Object Inheritance

One of the most powerful aspects of Object-Oriented programming is that we can utilize inheritance relationships as we create objects.  Inheritance relationships in real-world contexts help us to understand shared features that are the result of natural processes like evolution. OOP allows us to design our classes to take advantage of these natural relationships between classes.  If we look at relationships in evolutionary species, such as Darwin's finches, each successive generation becomes more specialized, yet each of the species still shares a group of common features with their common ancestor.  

As we design classes, we want to think about designing a base-class that can function as the parent class for one or more specialized child classes.  We see these relationships as the basis for how we classify and categorize objects in the world.  We might have a parent class called `Car`, this *base-class* would have properties and behaviors that are shared by all Car objects with properties like:  wheels, engine, seats, and behaviors like: drive, stop, refuel.  Then we could have child classes that were specialized types of cars: mini-van, sports-car, station-wagon, convertible-coupe...etc.

For our project, we'll look at inheritance in 2 cases.  We'll first create a generic Button class.  Then we'll create more specific types of Buttons:  PImageButtons and PShapeButtons.  These special Button child classes will allow us to add additional features compared to the generalized Button class.  

Our