#Drawing Application

Based on the simple button state example in the previous section, now we'll look at how we can use buttons to create user-interface behaviors in a customized drawing application.

###Types of Buttons
In the previous example, the button had distinct on and off states, and it controlled the color of an ellipse, this 2-state button (ignoring hover-states), is similar to a wall light switch, where we can look at the switch and observe that it's in 1 of 2 possible states.  We modeled this system with a 2-state finite state machine, where the states of the button were on or !on.  We also had additional hover-behavior that was also 

A different type of button is similar to a door-bell button: this type of button behaves in a more instantaneous manner, the button can be thought of as generating an impulse-type signal, sometimes referred to a 'bang' in data-flow systems.  This pulse can be used to trigger an event, but  



<a class="jsbin-embed" href="https://jsbin.com/vuqoyu/embed?js,output">JS Bin on jsbin.com</a><script src="https://static.jsbin.com/js/embed.min.js?3.34.3"></script>