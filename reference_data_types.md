#Reference vs Primitive Types

When we covered Functions, we discussed variable scope, we were discussing how primitive data type variables are defined as being visible, or available for use by the executing program.  Primitive data types are what we've been using so far: ``int, float, boolean, char``. When we have  

###Object Scope
 It is important to realize that when we pass `objects` into any function, then any modifications we make to that object will be *persisted* to the object after the function has finished executing.  In this respect, the rules of local and global variable scope don't affect objects, in the same way.  Objects are called reference-type variables.  This means that we can think of the labeled-box that stores our variable's value, instead of a value being stored in our box, instead, the address of another place in memory is stored in our 'variable-box'.  This address points to a specific address or memory location where our object's data is stored.  
 
###Object Memory-Storage
 This architecture is partially because objects represent much more complicated data-structures, and when the system executes our program, it may not know exactly how much memory space we need for each object that we create.  If we create a Menu object, we may choose to have the menu have 3 buttons, we may choose to have it hold 10 buttons, and we might not even decide how many buttons we want in our menu until the program is executing, so we'd be dynamically determining how large our Menu object is, and that could be different each time our program executes.