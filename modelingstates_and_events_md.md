##Finite State Machine

Below is a Finite state machine diagram a simple button application.
We want to implement this button using Processing.  The diagram below shows that the square button has 2 main states: 
       ``on=true``  or ``on= !true``
 When ``on=true``, the button is in the state on the left, where it is green.  We will add additional code so that the button turns dark green when the mouse hovers-over the button shape.  In addtion, the button also controls the color of an ellipse shape.  Since we're directly using the button state: ``on`` to control the color of the ellipse, then we've also included the ellipse within the button state of ``on``.  
 
 The arrows in the diagram represent events:  The events can cause the button to change state.  We have not identified a boolean state variable to store the current state of the mouseOver state / events.
 

![](fsm.png)