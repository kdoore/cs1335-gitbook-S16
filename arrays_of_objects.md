#Arrays of Objects

###Menu Buttons - Radio Group Logic
In the previous section, we discussed how to create a group of buttons which behave like radio buttons.  In our Menu class, we created 3 instances of Button objects, then we defined methods which explicitly called each method for the button object instances.  This is fine for our first pass at creating the Menu class, but once we figured out the required logic for implementing the button behavior, now we need to step back and analyze the code to see if we can make improvements. We can observe that the main function of the Menu class is to implement the Finite State Machine logic to control the activation of the group of Buttons: only 1 button can be active at any time, we need a state variable to remember which button is the currently active button.  

###Observations:

    1. Our Menu is not very extensible since we have hard-coded the Button creation logic within 
    the Menu class, we'd prefer flexibility in the number of buttons in our menu.
    
    2. When looking at our code, we observe that we're performing the identical operations on each
    button, this repetition of similar code suggests that using an Array and a loop could simplify
    our code and could provide more flexibility.
    
###Arrays as Constructor Parameter
For maximum flexibility for collections of objects like our Menu that is composed of Buttons, one powerful approach is that we can declare an Array of Buttons as an instance variable for the class, then we can have an Array of Buttons as an input parameter for the Menu Constructor.  This allows us to provide more specific configuration details for each button before adding it to the Menu.

```
//Create Class MenuArray 
class MenuArray{
    //instance variables
    Button[] btnArray;  //declare an array of Buttons
    int numButtons;     //how many Buttons are there?
    
    MenuArray( Button _btnArray, int _numButtons){
      btnArray=_btnArray;  //initialize instance variables with 
      numButtons=_numButtons;
    }
  //methods 
}
```

