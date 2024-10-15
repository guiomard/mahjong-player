## Project Context

**Describe the context of the problem domain here. Explain what you are proposing to do and your rationale for doing it. Explain why the problem domain is of interest.**

"Riichi Mahjong" is a traditional Japanese tile-based game based on luck, skill, strategy, and probability, analogous to a card game like Poker or Rummy. Riichi is a very complex game with a lot of depth based around making decisions from incomplete information. The heavy degree of chance involved means perfect decision-making is impossible; instead, a player can only compare probabilistic outcomes and make calculated risks, their judgement depending on the current state of the game.

The intention of this project is to design a heuristic-based AI capable of playing the game intelligently rather than using machine learning models. While machine learning-based Riichi AI models may offer greater potential for skilled play compared to heuristic-based approaches, there is a unique challenge in designing the algorithms, rules, and weights oneself rather than implementing a machine learning approach.

Riichi is traditionally a 4-player game, although it can be reduced to 3 or 2 players, and is a symmetric game meaning developing one AI model will allow 4 AI players to compete with each other sharing that model. Other AI models, either variations of my own or modified existing ones, may potentially be plugged into this project's game engine for the purposes of comparison via competition.

## Project Objectives

**Write out the key objectives of the project as bullet points. Each objective should be clear, realizable, and measurable/testable, i.e., the success of your project is determined by the degree to which these are realized.**

- Design a GUI that can render the game state and demonstrate the moves made by the AI visually.
- Implement the game engine including its rules and mechanics so that the state of the game can be sent to the AI for it to parse and make decisions off of.
- Develop a decision-making algorithm that allows the AI to compare possible moves and decide on the one most likely to result in a win.
- Optimize the algorithm to include advanced tactics and strategies beyond simple efficiency.
- Compare AI to existing models in order to track its performance across its development.

## Technologies & System Architecture

**Explain the technologies you are going to use and why you selected them. These include the programming languages, operating systems, presentation and storage technologies, and any cloud/3rd party libraries/services that you intend to use.**

Currently, Java is planned as the main programming language for implementing the game engine and AI algorithms, with JavaFX used for rendering the graphics. Java is chosen for its robustness, making it well-suited for handling heuristic AI, while also providing an opportunity to further enhance familiarity with the language.

The architecture would be made up of three components: the game engine layer, the AI layer, and the GUI layer. The game engine will handle the procedures of the game such as establishing the game state, managing the tiles, and giving each player their turn. The AI layer will make decisions based off of the game state it receives from the game engine using its heuristic strategies. The GUI should then render the game state, showing a top-down view of the board, each of the players' hands, and the tiles discarded by the players.