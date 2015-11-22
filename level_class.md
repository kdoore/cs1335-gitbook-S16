# Level Class

We want to add a Level class that acts as a data structure to keep track of all data relevant to each game level. 

We can add a variety of instance variables to the Level class.  We'll create an array of Level objects and a reference variable: curLevel to keep track of the current level.  

Level instance variables


Level[] levels = new Level[3];
levels[0] = new Level( 

We will change levels when all drops have either been caught (intersected) or have fallen below the bottom of the screen (finished).  In Shiffman's code, this is when:  levelCounter >= drops.length

This code below goes in the main tab, in the draw loop function, after the drop[i] loop code has ended.

```java


    // put in reset() function  //game method?
    // If all the drops are done, that leve is over! 
    if (levelCounter >= drops.length) {  //When levelCounter = 50
      //println("levelCounter inside if " + levelCounter);
      // Go up a level
      int maxLevels=levels.length-1;  //  if max index=1, maxLevels=1
      //println("levels length-1 " + (levels.length-1));
      //println("maxLevels " + maxLevels);
      if(curLevel.id +1 <= maxLevels ){  //go up a level if we have not hit the max level yet
        int index = ++curLevel.id; // increment to the next level ID and assign to indes
        println( "index " + index); //what is the next index
        curLevel=levels[index];  //change to next level
        println("curLevel changed " + curLevel.id);
      }
```

