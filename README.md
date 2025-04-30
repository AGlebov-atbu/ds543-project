# **Reinforcement Learning-Based Auto Chess Implementation**

*Boston University DS 543 Project, Spring 2025*  
*This project is maintained by students of Boston University: Aleksei Glebov and Kaya Daylor*

### **Goal**  

The goal of this project is to develop an Auto Chess agent using Reinforcement Learning (RL). **Auto Chess** is a strategy-based game that involves deploying units with different types, costs, abilities, and synergies, requiring the agent to make decisions on unit placement, itemization, and positioning. These decisions are based on game states which are constantly changing.  

This project will explore the development of an RL agent capable of performing well in Auto Chess while addressing challenges like delayed rewards and decision making under uncertainty.  

### **Reinforcement Learning Techniques**  

We propose using an RL approach tailored to a simplified Auto Chess environment with a defined economy, leveling system, and unit mechanics. A Deep Q-Network (DQN) would be able to handle the decision-making process, especially the shop decisions and money management. The agent needs to be able to evaluate the trade-offs between immediate rewards such as buying units and long-term rewards such as saving money.  

To address the multi-faceted nature of decisions, a DQN structure would separate state value estimation from specific action advantages. This would help distinguish between overall board states and individual moves. For handling the complex relationship between unit placement, synergies, and simplified abilities, we suggest using a neural network architecture that is able to recognize these patterns.  

### **Environment**  

We designed a custom Gymnasium environment that simulates a simplified Auto Chess game. The environment includes the following core mechanics:
- Shop system with randomized units based on the player’s level;
- Economy mechanics, including income, interest, and leveling costs;
- Unit management, such as placing, moving, and upgrading units via a so-called "star-system";
- Combat resolution, where units fight automatically based on proximity and attack range;
- Health tracking and game-ending conditions, creating clear win/loss signals.

Each environment step() processes a single player action, allowing the agent to gradually build strategies across multiple turns. The game ends when a player’s health drops to zero, providing a final reinforcement signal. Observations include numerical encodings of shop units, bench contents, board state, gold, health, and level.
