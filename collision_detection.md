# Collision Detection

In order to determine whether a collision has happened, each iteration of the draw loop requires that all active drops are tested to see if their geometry intersects with the geometry of the catcher or paddle object.  Shiffman's game used ellipse objects, so collision checking was a simple comparison between the distance between ellipse centers as compared to the radius of the 2 objects.  Since we're going to use PImage and PShape objects, which have rectangular geometry, then we need to redesign the collision tests for our objects.  

###Bounding Boxes
Since we're using .png images and svg graphics, these image formats allow for transparency, so our objects can visually appear smaller than the actual image dimensions.  For that reason, we want to add additional geometry variables that can be used to define a bounding box around our images, and it will be the bounding box dimensions that are used to determine if objects have overlapping geometry.

###Bounding Box Variables in Drop Base Class

Since we want to be able to test for intersection for any type of drop object, or for a child class of a drop object, then we need to create instance variables within the base class that can be inherited by any child classes.  

The following Drop Class instance variables will allow us to set bounding box dimensions as separate elements from the actual graphic element which might be a PImage or a PShape.  Then, in the child drop class, we can define bounding box dimensions which might be different than the actual png or svg graphic image.  Ideally, we would want to provide a constructor or method to set these values for child drops. 
```
bWidth // bounding box width
bHeight //bounding box height
bX //bounding box xPos
bY //bounding box yPos

