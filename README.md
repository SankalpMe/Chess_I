# Chess_I
It is a simple and elegant chessboard ui in html.
Behind the scene is a NodeJS backend, with a custom built UCI chess interface wrapper, that can interface with many chess engines.

In this project the NodeJS backend interfaces with a very famous chess engine , `stockfish` .
### Brief 
Basically it is a simple html ui having a chess board and few controls, while playing it allows users to invoke the `stockfish` engine to predict the best move for the current situation the board is.
It is like having a AI play the chess game for you.
The `stockfish` engine is extremely capable that your opponent stands almost no chance to win.

### Capabilities
The main purpose of this project was to learn about child processes and input output stream processing and piping.

A custom wrapper was written to command and process the output of the stockfish game engine to get the best move,
several features were implemented to deal with delays / errors in stockfish.
Nodejs was used to write all the wrappers and also as a backend for the HTML chess ui.

> Stockfish is a cli tool hence it has a command line interface unlike other packages with apis and library.
> In this project a std_input and std_output processing using child process was implemented in NodeJS to basically act like an wrapper.

The program deals with several hurdles of stream processing, and uses smart techniques to filter the required output from stockfish's `std_out` .

### HTML UI
![Chess_I UI](https://i.ibb.co/NyQsYvF/Screenshot-2021-09-28-at-10-41-23-PM.png)

1.  The UI has the main central board at the center, on this board pieces can be moved using drag and drop.
2.  Using `chess.js` a famous chess library for js, functionality like checking of check mate, check , a given move is valid is implemented.
3.  This client as soon as asked for computing a best move, sends http requests to the NodeJS backend with the board `fen`, a special way to store the chessboards current state, along with which players turn it is to play.
4.  The backend processes the result and returns them to the client, and then the client automatically moves the pieces as per the best move computed by `stockfish`
5.  The game also maintains a history of all the moves play, allowing players to revert there moves or glance back in history.
6.  As a aesthetic touch smooth animation are implemented in the history, and for piece transitions.

### Demo
![Demo GIF](/demo.gif)

Will load soon!
