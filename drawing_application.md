#Drawing Application

Based on the simple button state example in the previous section, now we'll look at how we can use buttons to create user-interface behaviors in a customized drawing application.

###Types of Buttons
In the previous example, the button had distinct on and off, visible behavior states, and it controlled 2 different color-states of an ellipse. This 2-state behavior button (ignoring hover-states), is similar to a wall light switch, where we can look at the switch and observe that it in 1 of 2 possible physical configuration states.  We modeled this system with a 2-state finite state machine, where the states of the button were `on` or `!on`. 

A different type of button is similar to a door-bell button: this type of button behaves in a more instantaneous manner, the button can be thought of as generating an impulse-type signal, sometimes referred to a 'bang' in data-flow systems.  This pulse can be used to trigger an event, but it doesn't  



<a class="jsbin-embed" href="http://jsbin.com/vuqoyu/edit?js,output">JS Bin on jsbin.com</a><script src="http://static.jsbin.com/js/embed.min.js?3.34.3"></script>