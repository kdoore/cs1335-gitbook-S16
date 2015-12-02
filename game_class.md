# Game Class

We can refactor Shiffman's game code to provide a cleaner, more modular structure that is easier to understand, troubleshoot, and to extend.


- score: int // current score
- level:int // level the game is currently in
- state: int // Game can be in inactive or active state
- numberDropsDone: int// a drop is done if it is caught by the catcher or if it reaches the bottom of the canvas (this is called levelCounter in 10.4)
- numberLivesLeft: int// counter value initialized at MAX_NUMBER_LIVES and decremented when a drop reaches the bottom. (this is called lives in 10.4)
- totalDrops: int // number of drops generated
- gameOver: boolean// set to true when a game is over
- Wbar: float// width of the background bar behind the buttons
- startBtn: LabeledButton // Button to start the game
- stopBtn: LabeledButton // Button to stop the game
- paddle:Paddle// Paddle class
- timer: Timer// Timer class
- drops: array of drop objects // size of array is MAX_NUMBER_DROPS
 

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
      reset();  //initialize values
    }

```
Game Class Methods: 

  
  
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
    }  //end of else(!gameOver)
  
  game.drawBar();
  game.drawButtons();
  }  //end of Draw loop

  void mouseClicked(){
    game.buttonClick(mouseX, mouseY);
  }
 
```
