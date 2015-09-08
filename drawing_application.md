#Drawing Application

Based on the simple button state example in the previous section, now we'll look at how we can use buttons to create user-interface behaviors in a customized drawing application.

##Programming Project

Currently, the drawing application below has a default brush pattern which is drawn when the mouse is pressed and it is over the drawing-canvas area.  Extend the program below to include 3 different pattern buttons, where one pattern functions as an eraser by drawing white ellipses.   It will be necessary to add a new state variable: ``activePattern`` to keep track of the currently selected pattern. Three buttons can be created to allow the user to select which pattern should be active.  In the mouseClicked event, it will be necessary to check to see which button is activated if a user clicks to change the brush pattern.  


<a class="jsbin-embed" href="http://jsbin.com/vuqoyu/edit?js,output">JS Bin on jsbin.com</a><script src="http://static.jsbin.com/js/embed.min.js?3.34.3"></script>