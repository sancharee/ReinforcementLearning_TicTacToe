# ReinforcementLearning_TicTacToe
Build an RL agent that learns to play Numerical Tic-Tac-Toe with odd numbers 


![tictactoe](https://user-images.githubusercontent.com/16771458/224541991-11742b16-2e34-4782-b9a9-209f1d2f0a4c.jpg)

One of the most popular and enduring games of all time is Tic-Tac-Toe. Because of its familiarity, this game is often used as a starting example to mathematically analyze a decision-making process. Its brevity makes it a perfect game to illustrate the rewards of thinking ahead and learning the consequence of each decision.<br>
A popular variant of this game is Numerical Tic-Tac-Toe. Instead of X’s and O’s, the numbers 1 to 9 are used. In the 3x3 grid, numbers 1 to 9 are filled, with one number in each cell. The first player plays with the odd numbers, the second player plays with the even numbers, i.e. player 1 can enter only an odd number in the cell while player 2 can enter an even number in one of the remaining cells. Each number can be used exactly once in the entire grid. The player who puts down 15 points in a line - (column, row or a diagonal) wins the game. <br>

### Rules of the Game:
- The game will be played on a 3x3 grid (9 cells) using numbers from 1 to 9. Each number can be used exactly once in the entire grid.

- There are two players: one is the Reinforcement Learning (RL) agent and other is the environment.

- The RL agent is given odd numbers {1, 3, 5, 7, 9} and the environment is given the even numbers {2, 4, 6, 8}

- Each of them takes a turn. The player with odd numbers always goes first.

- At each round, a player puts one unused number on a blank spot.

- The objective is to make 15 points in a row, column or a diagonal. The player can use the opponent's numbers in the grid to make 15.

- The game terminates when any one of the players makes 15.
 

This model builds an RL agent that learns to play Numerical Tic-Tac-Toe with odd numbers (the agent will always make the first move). The agent needs to be trained using Q-Learning. The environment is playing randomly with the agent, i.e. its strategy is to put an even number randomly in an empty cell. If your agent wins the game, it gets 10 points, if the environment wins, the agent loses 10 points. And if the game ends in a draw, it gets 0. Also, you want the agent to win in as few moves as possible, so for each move, it gets a -1 point.

Following is a sample episode for  reference: 
![084eb86a-ba5b-4d96-90ce-49695e71f370-Assignment3](https://user-images.githubusercontent.com/16771458/224542534-3349760d-0efb-4d24-9c6d-4bdb6a16deeb.png)

In this episode, the environment wins as it is able to make 15 first (8+6+1).<br> After the agent places 1 in one of the grids, the environment rewards it (with a negative reward of -1) and makes a next move of placing 8 in one of the remaining cells.

### Steps in Model Development

* Create an MDP for Numerical Tic-Tac-Toe game. The basic framework for this is:

    * Initialise the state

    * Define the action space for each state. 

    * Define the winning states: the sum of three numbers in a row, column or diagonal is 15.

    * Define the terminal states (win,tie,loss)

    * Build the reward structure as below:

        * +10 if the agent wins (makes 15 points first)

        * 10 if the environment wins

        * 0 if the game ends in a draw (no one is able to make 15 and the board is filled up)

        * -1 for each move agent takes

    * Define a step function which takes in an input of the agent’s action and state; and outputs the next state and reward. 
* Build an agent that learns the game by Q-Learning.
    * While updating the Q-values, if the next state is a terminal state, then the Q-values from that state are 0. (No action is possible from that state)
* **Q-values convergence**- Finally the  4 state-action pairs are plotted  with the number of episodes to understand the convergence.
 
