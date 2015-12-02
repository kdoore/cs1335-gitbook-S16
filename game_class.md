# Game Class

We can refactor Shiffman's game code to provide a cleaner, more modular structure that is easier to understand, troubleshoot, and to extend.

 

Game Class Constructor:

```
class Game{
  int state;
  int score;
  int numberDropsDone; // levelCounter
  int numberLivesLeft;
  int totalDrops=0;
  int wbar;
  final int ACTIVE=1;
  final int INACTIVE = 0;
  final int MAX_NUMBER_DROPS=50;
  Level[] levels;
  Level curLevel;
  Paddle paddle;
  PImage starImage;
  int btnHeight=30;
  Button startBtn, stopBtn;
  boolean gameOver;
  Drop[] drops;
  Timer timer;
  
  Game(){
     state = INACTIVE;
      wbar = width/7;
      initializeLevels();
      startBtn = new Button(width - wbar + 5, 10, 40, btnHeight);
      stopBtn = new Button(width - wbar + 5, 50, 40, btnHeight);
      PImage paddleImage=loadImage("girl1.png"); 
      paddle = new Paddle(200, 300, 252, 285, paddleImage);
      starImage= loadImage("star.png");
      drops = new Drop[MAX_NUMBER_DROPS];    // Create spots in the array
      timer = new Timer(300);   // Create a timer and set initial value to 300 milliseconds
      gameOver = false;
      resetLevel();  //initialize values
    }

```
Game Class Methods: 
```
 void initializeLevels(){
      PImage bkg1 = loadImage("background_b1.png");
      PImage bkg2 = loadImage("background_teal.png");
      levels = new Level[2];
      levels[0]= new Level(0,30,color(#5F6795),bkg1);
      levels[1]= new Level(1,10,color(#5F9594),bkg2);
      curLevel=levels[0];
    }
    
    //use to reset values for new level
    void resetLevel(){
      numberLivesLeft = curLevel.lives;
      numberDropsDone = 0;
      timer.setTime(constrain((300-curLevel.id*25),0,300));
      totalDrops = 0; 
    }
    
    //use to reset entire game
    void resetGame(){
      curLevel=levels[0];
      score=0;
      resetLevel();
      startBtn.on=false;
      stopBtn.on=false;
    }
    
    void drawBackground(){
    
    }
    
    void play(){
    
    }
    
    void displayScore(){
    
    }
    
    void displayLevel(){
    
    }
    
    void displayGameOver(){
    
    }
    
    void drawBar(){
    
    }
    
    void drawButtons(){
    
    }
    
    void buttonClick(){
    
    }

    
 ``` 

Game play() method

```
void play(){
               if(keyPressed){
                if (key == CODED) {
                    paddle.PaddleKeyPressed();
                   }  
                } //end of if keypressed
            paddle.display();
     
            if (timer.isFinished()) {
              // Deal with raindrops
              // Initialize one drop
              float rand=random(0,1);
              if (totalDrops < drops.length) {
                 if(rand > 0.5){
                    drops[totalDrops] = new ImageDrop(starImage, 97,97);
                 }else{
                    drops[totalDrops] = new Drop();
                 }
                // Increment totalDrops
                totalDrops++;
              }
              timer.start();
            }
            ////Start of drops loop
            // Move and display all drops
            for (int i = 0; i < totalDrops; i++ ) {
              if (!drops[i].finished) {
                drops[i].move();
                drops[i].display();////// 
                if (drops[i].reachedBottom()) {
                  numberDropsDone++;
                  drops[i].finished(); 
                  // If the drop reaches the bottom a live is lost
                  numberLivesLeft--;
                  // If lives reach 0 the game is over
                  if (numberLivesLeft <= 0) {
                    gameOver = true; 
                  }
                } 
              // Everytime you catch a drop, the score goes up
                if (paddle.intersect(drops[i])) {
                  drops[i].finished();
                  numberDropsDone++;
                  score++;
                }
              }
            }////end of the drop[i] loop
        
            // If all the drops are done, that leve is over!
            if (numberDropsDone >= drops.length) {
              // Go up a level
              int maxLevels=levels.length-1;  //  if max index=1, maxLevels=1
          
              if(curLevel.id +1 <= maxLevels ){  //go up a level
                int index = ++curLevel.id;
                curLevel=levels[index];
                println("curLevel changed" + curLevel.id);
              }
             
             resetLevel();
            }
    }//end game.play()
    

```
  
MainTab Code:
```
Game game;

void setup() {
  size(400,400);
  game = new Game();
}

void draw() {
  game.drawBackground();
  
  if (game.gameOver) {
    game.displayGameOver();
  } 
  else {
     game.play();
     game.displayScore();
     game.displayLevel();
    }  //end of else
  
  game.drawBar();
  game.drawButtons();
  }  //end of Draw loop

  void mouseClicked(){
    game.buttonClick(mouseX, mouseY);
  }
 
```
