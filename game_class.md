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