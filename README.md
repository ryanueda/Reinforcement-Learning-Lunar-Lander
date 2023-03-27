# Reinforcement-Learning-Lunar-Lander
Reinforcement Learning For OpenAI's Lunar Lander

Link to Technical Paper: [Technical Report](https://github.com/ryanueda/Reinforcement-Learning-Lunar-Lander/blob/main/Reinforcement%20Learning%20Paper.pdf)

## About OpenAI's Lunar Lander
OpenAI Lunar Lander is a reinforcement learning environment that simulates the classic arcade game of landing a spacecraft on the surface of the moon. In this environment, an agent (e.g. a machine learning algorithm) is trained to control the spacecraft and make decisions about when to apply thrust and how much to apply in order to safely land the spacecraft. The agent receives rewards for successfully landing the spacecraft and penalties for crashing or using too much fuel. Through trial and error, the agent learns to optimize its actions in order to maximize the rewards it receives. This type of problem is well-suited for reinforcement learning, as the agent must learn to adapt its actions based on the consequences of those actions.


# Introduction To Q-Learning
## Q-Learning Overview
The Q-Learning algorithm uses a Q-table of State-Action Values, otherwise known as the Q-values. This table has a row for each state and a columnm for each action. 
Each cell contains the estimated Q-value for the corresponding state-action pair.

All Q-Values are set to zero initially. As the agent interacts and gets feedback, the algorithmthen iteratively improves these values until they converghe with the Optimal Q-Values. It then updates them using the Bellman Equation.

## Q-Learning Algorithm
Q-Learning finds the optimal policy by learning Q-Values for each state-action pair.

- Initally, agent randomly picks actions
- Upon interacting with env, learns which actions are better based on rewards obtained. These exps are used to incrementally update Q-Values
- Equation used to update these values are based off the Bellman Equation
- Two main actions in Q-Learning:
  - Current Action: action from which current state that is executed, and whose Q-Value is updated
  - Target Action: has highest Q-Value from next state, used to update current action's Q-Value
  
## Why Do Estimates Become More Accurate Over Time?
Although we start with arbitrary estimates, at every time-step, the estimates become slightly more accurate as they get updated with real-time obsevations

The update formula combines these 3 terms in weighted proportions:
- Reward For Current Action
- Best Estimated Q-Value of Next State-Action
- Estimated Q-Value of Current State-Action

Although 2/3 of these values are estimates, one of them, the reward of the current action, is concrete real data, used to update the Q-Values




# Deep Q Network (DQN)
The Deep Q Network (DQN) works similarly to Q-Learning. However since its a neural network, it uses a Loss function instead of an equation. It also uses the Q-Values to compute Loss in order to train the network, improving its predictions
In this case, the Loss refers to the Mean Squared Error (MSE) between the Target Q Value and the Predicted Q Value

## Architechture Of A DQN
The DQN architecture consists of two neural networks, the Q network, the Target network, and Experience Replay. 
The Q network is the agent trained the produce the Optimal State-Action Value, while the Expereince Replay is used to generate data to train the Q Network by interacting with the environment
The Target network is identical to the Q network


REFERENCES:
- https://towardsdatascience.com/reinforcement-learning-explained-visually-part-4-q-learning-step-by-step-b65efb731d3e
- https://towardsdatascience.com/reinforcement-learning-explained-visually-part-4-q-learning-step-by-step-b65efb731d3e
