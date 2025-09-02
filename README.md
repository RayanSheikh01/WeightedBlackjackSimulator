# Blackjack AI vs. Cheating Dealer Simulator

This project uses a Python-based simulation to analyse the game of Blackjack against a dealer with a weighted, "cheating" deck. It first quantifies the dealer's advantage and then trains a Reinforcement Learning (Q-learning) agent to develop an optimal strategy to overcome the unfair odds.

---

## Overview

The simulation follows two main stages:
1.  **Baseline Analysis**: A simple, fixed player strategy ("hit until 17") is simulated over tens of thousands of rounds against a dealer whose deck is weighted to favour high-value cards. This establishes a clear, statistical measure of the dealer's advantage.
2.  **AI Training & Evaluation**: A Q-learning agent is trained against this same cheating dealer. The agent learns an optimal policy for when to "hit" or "stand" to maximise its win rate. The performance of this learned strategy is then compared to the initial baseline, demonstrating a significant improvement in player outcomes.

---

## Key Features

-   **Weighted Deck Simulation**: Models a "cheating" dealer with an increased probability of drawing high cards.
-   **Q-Learning Agent**: Implements a reinforcement learning model to train an AI player and discover a superior strategy.
-   **Strategy Comparison**: Provides a direct statistical and visual comparison of the naive strategy vs. the trained AI strategy.
-   **Data Visualisation**: Uses `matplotlib` and `pandas` to generate clustered bar charts comparing win/loss outcomes.
-   **Hyperparameter Tuning**: Includes a random search to find the most effective learning parameters for the Q-learning model.

---

## Technologies Used

-   **Python 3**
-   **Jupyter Notebook**
-   **Pandas**: For data manipulation and analysis.
-   **Matplotlib**: For data visualization.

---

## Setup and Usage

To run this simulation on your local machine, follow these steps:

**1. Clone the repository:**
```bash
git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
cd your-repository-name
```

**2. Create and activate a virtual environment (optional but recommended):**
```bash
# For Windows
python -m venv venv
.\venv\Scripts\activate

# For macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

**3. Install the required dependencies:**
Create a file named `requirements.txt` with the following content:
```
pandas
matplotlib
jupyter
```
Then, run the following command in your terminal:
```bash
pip install -r requirements.txt
```

**4. Run the Jupyter Notebook:**
```bash
jupyter notebook weightedBlackjackSimulator.ipynb
```
Once the notebook is open, you can run the cells sequentially to see the simulation, training and analysis.

---

## Results and Conclusion

The simulation demonstrates that a trained AI can significantly counter the disadvantage imposed by the cheating dealer.

-   **Initial Disadvantage**: With a simple "hit until 17" strategy, the player only won **~37%** of games, while the cheating dealer won **~52%**.
-   **Learned Strategy**: The Q-learning agent developed a conservative strategy, learning to **stand on any hand total of 12 or higher**.
-   **Improved Performance**: Using this AI-driven strategy, the player's win rate increased to **~45%**, effectively mitigating a large portion of the dealer's unfair advantage.

> This project serves as a practical demonstration of how reinforcement learning can be used to develop an adaptive strategy that significantly improves outcomes in a game of chance, even against a biased opponent.

---

## Future Improvements

-   **Implement More Actions**: Expand the agent's action space to include "double down," "split," and "surrender."
-   **Advanced RL Models**: Explore more complex algorithms like Deep Q-Networks (DQN) to see if a more nuanced strategy can be learned.
-   **Card Counting**: Add a state for the deck's card count to allow the agent to learn card-counting strategies.
