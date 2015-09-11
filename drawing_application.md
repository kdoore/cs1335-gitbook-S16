#Drawing Application

Based on the simple button state example in the previous section, now we'll look at how we can use buttons to create user-interface behaviors in a customized drawing application.

##Programming Project

Currently, the drawing application below has a default brush pattern which is drawn when the mouse is pressed and it is over the drawing-canvas area.  Extend the program below to include 3 different pattern buttons, where one pattern functions as an eraser by drawing white ellipses.   It will be necessary to add a new state variable: ``activePattern`` to keep track of the currently selected pattern. Three buttons can be created to allow the user to select which pattern should be active.  In the mouseClicked event, it will be necessary to check to see which button is activated if a user clicks to change the brush pattern.  


<a class="jsbin-embed" href="http://jsbin.com/vuqoyu/edit?js,output">JS Bin on jsbin.com</a><script src="http://static.jsbin.com/js/embed.min.js?3.34.3"></script>


###Starter Code for Project 1 - Drawing Application

```

//create variables for hsb color values
int  bright, dark;
boolean clearButtonOn; // clear button state
int activeBrush; 
static final int  pattern1=0;   //use as activeBrush state indicator
static final int  erase=1;      //use as activeBrush state indicator
int bwidth, bheight, menuX;  //menu dimensions
int  clearBtnY;  //clear button y postion
int  pattern1BtnY;// pattern1 button y position
int  eraseBtnY; //eraser button y position


void setup () {
    size (400, 300);
    colorMode(HSB);
    background (255, 0, 255);  //white in HSB
    bright=255; dark=180;  //brightness values for HSB hover change
    fill (255, 255,bright);        // start with red meaning it's off
    clearButtonOn=false;
    bwidth=100; bheight=height/3;  //set button width and height
    menuX=width-bwidth;  // x position for menu buttons
    clearBtnY=0;   // y position for clearBtn
    pattern1BtnY=clearBtnY + bheight;  //start y position for pattern1 Btn
    eraseBtnY=clearBtnY + (2* bheight);  //start y position for eraseBtn
    activeBrush=pattern1;
    smooth();
}

void draw () {
   if(clearButtonOn==true){  //check if clear button is active
     clearCanvas(0, 0,width, height);
   }
   drawBrushPattern();
   drawMenu(menuX,0, 100, height);
   //draw menu buttons last
   drawP1Button(menuX, pattern1BtnY, bwidth, bheight);
   drawEraseButton(menuX, eraseBtnY, bwidth, bheight);
   drawClearButton (menuX, clearBtnY,bwidth, bheight);   
}

//test to see what brush is active, call that function
void drawBrushPattern(){
   
}

// test if mousePressed, test if over canvas, draw some pattern at mouseX,mouseY
void drawPattern1(){
   
}

// test if mousePressed, test if over canvas, draw some pattern at mouseX,mouseY
void drawEraser(){
  
}
//draw a black rectangle as background for buttons
void drawMenu(int _x, int _y, int _width, int _height){
       fill(0);  //black
       strokeWeight(1);
       stroke(100);
       rect(_x, _y, _width, _height);
}

//draw the pattern for the clearCanvas button, make sure to include hover behavior
void drawClearButton (int _x, int _y, int _width, int _height) {
  fill(255);
  rect(_x, _y, _width, _height);  //background rect
  stroke(255, 255,bright);
   // check to see if the mouse is over the button
  if ((!mousePressed) && (mouseX > _x && mouseX < (_x + _width) && (mouseY > _y && mouseY < (_y+_height)))){
        stroke(255, 255, dark); // hover color
    }
   //draw button shape - Erase Symbol
    strokeWeight(12);
    float _center=_width/2;
    translate(_x+_center, _y+_center);
    ellipse(0, 0, _width-20,_width-20);
    rotate(degrees(-45));
    rectMode(CENTER);
    rect(0,0,70, 2);
    rectMode(CORNER);
    resetMatrix();
  }
 
  //draw shape for P1 button, should have 1 design when activeBrush==pattern1, and 
  // a different design when activeBrush != pattern1
 void drawP1Button(int _x, int _y, int _width, int _height){
  
  
 }
 
 //draw shape for P1 button, should have 1 design when activeBrush==pattern1, and 
  // a different design when activeBrush != pattern1
void drawEraseButton(int _x, int _y, int _width, int _height){
 
 }

void clearCanvas (int _x, int _y, int _width, int _height) {
     noStroke();
    fill(255,0,255,240);  
    rect (_x, _y, _width, _height );
    clearButtonOn=!clearButtonOn;  //change button state to off   
}

void mouseClicked (){
   //check global dimensions of clear button 
   if (mouseX > menuX && mouseX < (menuX + bwidth) && (mouseY > clearBtnY && mouseY < (clearBtnY+bheight))){
      clearButtonOn=!clearButtonOn;   //change button state to on
      println ("clear button state " + clearButtonOn);
      } 
      //now check to see if mouse is over either other button and if so, then change state 
      //of activeBrush
      /*
      //if mouseX,mouseY on pattern1 : activeBrush==pattern1
     if(){
       
     }
     //if mouseX,mouseY on erase : activeBrush==erase
     else if(){
       
     }
      */
    }
   ```