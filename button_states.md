Button States
==============

In this project, we'll look at button states like hover, pressed, and clicked, as well as how buttons can be used to provide users with control over states of other elements of our programs. This project continues to emphasize the use of functions to create modular code. In a future version of this project, we'll create object-oriented buttons. As this project shows, it is helpful to think of buttons as having different behaviors such as display color depending on their current state and user interaction. It is instructive to consider how a button differs from a simple rectangle, code written for the button directly relates to the behaviors and functions of a button when contrasted with a simple rectangle.

 Below is one possible way we could describe or model the features of a button:

  **Function:**  
  -   Indicate and allow change of State for some system variable
 

  **Behaviors:**  
  -   Default, Hover, MousePressed, MouseClicked
 

  **Structure:**  
  -   Square defines activation area
  -   Fill and stroke changes to indicate behavior and state
  -   Position is defined with x,y coordinates on the canvas
  -   Size is defined by some width and height values
 
Here, we will use global variables to maintain these button states, yet intuitively, it would make sense that the button display state information should only be used within the code to display the button.

In the code below, we create a very simple program with 2 rectangles to explore how to design a button. We want the button to respond to the user's mouse when the mouse interacts with the button's rectangular area to give the user indication that the button is interactive. We will have 2 types of dynamic behavior in this project, one set of behaviors relate to how the button rectangle changes with mouse interaction. Then, we need to have the button change the state of the blue rectangle, using the global state variable `rectState` :

