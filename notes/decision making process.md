## AI Discard Decision Algorithm Design

The following outlines a proposed design for the AI's decision-making process when selecting a discard in Riichi Mahjong. The AI could calculate key scores for each possible discard to make informed decisions. These scores could be used to evaluate the potential outcomes of each discard.

### 1. **Win Probability**
The AI could calculate the probability of winning the hand based on each discard option.

- **Method**: A **Monte Carlo simulation** could be utilized to estimate the winning probability. If there are N draws remaining in the game, N tiles could be randomly drawn, and the AI could check if a winning hand can be formed using the current 13 tiles plus the N drawn tiles. This process could be repeated 1000 times to ensure statistical significance.
- **Optimization**: To improve efficiency, the "tiles needed to complete the hand" could be pre-calculated, allowing the simulation to check only if any of these necessary tiles appear in the N randomly drawn tiles.

### 2. **Average Winning Points**
The AI could estimate the average number of points it would score if it wins with a given discard.

- **Method**: During the same Monte Carlo simulation used for calculating Win Probability, the AI could also track the number of points gained from a winning hand. By averaging these points over 1000 simulations, the AI could estimate the expected score if it wins with the current discard.

### 3. **Discard Risk**
The AI could evaluate the likelihood that discarding a particular tile would allow an opponent to win, particularly opponents who have declared **Riichi**.

- **Method**: A **decision tree learning model** could be implemented to estimate the risk of discarding each tile. The model could be trained by accounting for things like Doras, tiles near a discarded riichi call or using Suji defensive play.
- **Justification**: This probabilistic model could enable the AI to make decisions that balance offensive and defensive play, reducing the risk of discarding into an opponent's winning hand.

### 4. **Average Loss Points**
The AI could predict the average points lost if it discards a tile that allows an opponent to win.

- **Method**: Initially, a fixed value of 6265 points could be used, derived from historical logs of games. This value represents the average point loss when a player discards a winning tile to an opponent. Over time, this value could be dynamically adjusted based on real-time game conditions and additional data from the AI’s simulations.
- **Implementation**: This could serve as a risk metric, helping the AI make safer decisions in high-risk situations.

---

This proposed design ensures the AI could make decisions based on statistical data, combining both offensive potential (winning chances and points) and defensive considerations (risk of dealing into a winning hand). Each of these metrics could be calculated for all possible discards to optimize the AI’s performance in various game scenarios.
