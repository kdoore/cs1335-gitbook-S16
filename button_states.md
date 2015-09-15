Button States
==============

In this project, we'll look at button behaviors like hover, pressed, and clicked, as well as how buttons can be used to provide users with control over states of other elements of our programs. This project continues to emphasize the use of functions to create modular code. In a future version of this project, we'll create object-oriented buttons. As this project shows, it is helpful to think of buttons as having different behaviors such as display color depending on their current state and user interaction. It is instructive to consider how a button differs from a simple rectangle, code written for the button directly relates to the behaviors and functions of a button when contrasted with a simple rectangle.

 Below is one possible way we could describe or model the features of a button:

  **Function:**  
  -   Indicate and allow change of State for some system object or variable
 

  **Behaviors:**  
  -   Display Color of Button:  Default, Hover, MousePressed, MouseClicked
 

  **Structure:**  
  -   Square defines activation area
  -   Fill Color changes to indicate mouse-behavior and state
  -   Position is defined with x,y coordinates on the canvas
  -   Size is defined by some width and height values
 
Here, we will use global variables to maintain these button states, yet intuitively, it would make sense that the button display state information should only be used within the code to display the button.

In the code below, we create a very simple program with a rectangle button and an ellipse, who's display color is controlled by interacting with the button. 

We want the button to display some behavior in response to the user's mouse when the mouse hovers over the button's rectangular area to give the user indication that the button is interactive. We will have 2 types of dynamic behavior in this project, the first set of behaviors relate to how the button's displayed rectangle changes color with mouse interaction. Second, we also need to have the button-state control the display state of the ellipse, using the global state variable `on` :

We are using the colorMode(HSB) so that we can simplify the code for the hover behavior, where we simply modify the HSB `Brightness` parameter when the user's mouse is positioned directly over the button.  

<a class="jsbin-embed" href="http://jsbin.com/yizuce/edit?js,output">Code Example on jsbin.com</a><script src="http://static.jsbin.com/js/embed.min.js?3.34.2"></script>

{%ace edit=false, lang='java'%}
// This is a simple button program where the button controls the //color of the ellipse.  
// The button color is green when the button is on, and red when it's not on.
// The button also displays 'hover' behavior.

// Declare Global Variables
//create variables for hsb color values
int hueValue,red, green, brightValue,light, dark;

boolean on;  //buttonState
int x, y, bwidth, bheight;

void setup () {  //initialize all values
    size (400, 400);
    colorMode(HSB);   //use HSB colorMode
    background (255, 0, 255);
    red=255; green=100;
    light=255; dark=100;
    brightValue=light;   //initialize to bright
    hueValue=red;       // initialize to red
    fill (hueValue, 255,brightValue);  // start with bright red meaning it's off
    on=false;       //initialize to off
    //button physical dimensions
    x=50;y=50;
    bwidth=50; bheight=50;
    stroke(150); 
}

void draw () {
   drawButton (x, y, bwidth, bheight); 
   drawEllipse(250, 250, 100, 100);
}

//Draw 
void drawButton (int _x, int _y, int _width, int _height) {
  if(on){  //checking global button state
        hueValue=green; // on color
        }   
        else{
            hueValue=red; // off color
         }
   // check to see if the mouse is over the button
  if ((mouseX > _x && mouseX < (_x + _width) && (mouseY > _y && mouseY < (_y+_height)))){
        brightValue=dark;  //dark hover color
    }
    else{
        brightValue=light; //default bright color
    }
  fill(hueValue, 255, brightValue);  //set fill with hueValue, brightValue
  //draw button shape
  rect(_x, _y, _width, _height);
  }

void drawEllipse (int _x, int _y, int _width, int _height) {
  if(on){
    fill(60,255,255);  //limeGreen color
  }
  else{
     fill(200,255,255); //purple color
  }
  ellipse (_x, _y, _width, _height );
}

 //Event Handler Code
void mouseClicked (){  
   //check global dimensions of button 
   if (mouseX > x && mouseX < (x + bwidth) && (mouseY > y && mouseY < (y+bheight))){
      on=!on; //change the button state
      println ("button state " + on);  
      } 
    }

{%endace%}




