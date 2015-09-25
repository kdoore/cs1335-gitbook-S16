#Menu Object with Buttons

Now that we've created our button class, which is our template to create button objects, it's time to leverage our hard work to simplify the drawing application

###Composition:  Menu Has Button Objects
We will create a Menu class, and it will be composed of a set of button objects.  The button objects are responsible for most of their behavior, however, since we want these buttons to work together as a radio-button type menu, we're going to have to add some additional logic to the Menu class to insure that only 1 button is active at a time.  

###Menu Buttons Finite State Machine

![](MenuFSM.png)
The image above shows that the 3 Menu-Button objects must work together, only 1 button can be active at a time.  If Button 1 is currently active, then the events:  Click2 or Click3 will change the Menu-State.  In the Menu class, we need to implement a state variable:  ActiveButton which will store the current-state:  activeButton.  In addition, we must supply logic so that when these events happen, the other buttons are de-activated.   

### Menu Code: 
In the code below, we have created the Menu Class, we've added 3 button objects, they are initialized in the constructor and we've created a display() and click() method.  However, right now these buttons don't have the required logic needed for them to function as a menu.  Right now these buttons each work independently.  

What code do we need to add to create the radio button behavior?
```
class Menu{
  
  Button btn1, btn2, btn3;
  float xPos, yPos, btnSize;
  
  Menu( float _xPos, float _yPos, float _btnSize){
          btn1= new Button(_xPos, _yPos, _btnSize, _btnSize);
          btn2= new Button(_xPos, _yPos+_btnSize, _btnSize, _btnSize);
          btn3= new Button(_xPos, _yPos + (2*_btnSize), _btnSize, _btnSize);
  }
  
  void display(){
    btn1.display();
    btn2.display();
    btn3.display();
  }
 
  void click(int mx, int my){
       btn1.click(mx, my);
       btn2.click(mx, my);
       btn3.click(mx, my);
  }
  
}  //end class

```
