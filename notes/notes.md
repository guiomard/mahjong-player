# Project Planning

## Overview
The end goal for the project would be a program that allows 4 differently-trained ai models designed by me to compete against each other to determine the most effective one. Failing that, even designing one competent ai model could be acceptable, although I would then want to implement a way for a user to play against it.

## The Game
Mahjong is a turn-based tile game where 4 players compete to be first to assemble a winning hand. 
- A player as a hand of 13 tiles and must draw and discard a tile each turn. 
- There are three suits of tiles numbered 1 to 9 as well as 7 special tiles, there are 4 copies of each tile.
- A winning hand consists of four sets of 3 tiles of a suit (either a sequence like 1, 2, 3 or a triplet like 1, 1, 1) and a pair
- When a tile that completes the above criteria is drawn or discarded by an opponent, the player may declare the win and the round is over
- The winning player earns points dependant on how many conditions their hand fulfilled
- If no player completes a hand, the round ends when there are no more tiles to draw.
- There are 8 rounds in total
- There are several exceptions to most things listed above.

## Rough Model
**Information Sending**:
At the start of the game the ai would need to know its seating position, which determines the turn order. At the start of the round the ai player would need to know the overall state of the game such as the round number and each players' score and a few miscellaneous details. Then they would need to be updated each turn, both their own turn and the other players' turns. The sent information would be something like this.
- [1] *Game Start*: seat position
- [2] *Round Start*: current round, player scores, dora indicator
- [3] *The AI Player Turn*: the tiles in hand, the drawn tile
- [4] *Other Player Turn*: discarded tile
The ai would need to make a decision at [3] on which tile to discard. Additionally, there would be points where it would have the option to call other players' discards, so they would be prompted to make a choice at [4] although only occasionally.

**Decision Making**
There are three vectors of discard decision making in mahjong: speed, score and safety. Speed is how fast you can assemble a winning hand, Score is how valuable a winning hand would be and Satety is how likely an opponent is to win off of the tile you deal.
The ai would need to balance these vectors, and the optimal balance is dynamic depending on the game state.
The ai would need to have a list of *yaku* (the conditions that determine a hand's score). 

**Designing the AI**
From the outset I foresee a few types of computational intelligences that could be used
- Basic Heuristic Model 
- Reinforcement Learning Model (w/ something like Monte Carlo Tree Search)
- Trained Model via Data Sets
Reinforcment seems the most promising as I don't have access to a large data set of mahjong matches as of yet.


## Milestones
1. **Milestone 1**: Initial planning
   - Task 1: Set up project repository
   - Task 2: Research currently existing mahjong ai
   - Task 3: Decide on a language and framework

2. **Milestone 2**: Game Development
   - Task 1: Design game logic
   - Task 2: Develop game engine

3. **Milestone 3**: AI Design
   - Task 1: Design ai logic
   - Task 2: Implement ai
   - Task 3: Allow ai to compete
   - Task 4: Record results

3. **Milestone 4**: UI design
   - Task 1: Design ui to visualize games

   ## Roadmap
- **Implement basic GUI** : GUI capable of rendering a game state.
- **Implement basic game engine** : Basic game engine capable of managing tiles and player turns
- **Integrate game engine with GUI** : GUI that renders a game being run
- **Develop game engine** : Game engine with rules and discard mechanics
- **Implement basic AI** : Basic AI capable of choosing tiles
- **Integrate AI with game engine** : Game engine being played by AI players, rendered by a GUI
- **Refine game engine** : Full game functionality implemented
- **Develop AI** : Implemented heuristic decision-making
- **Compare & Test AI** : Identified the performance of the AI
- **Optimize AI** : Optimized AI based on testing
- **Refine GUI** : Polished render of game state