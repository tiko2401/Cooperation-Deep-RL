# Cooperation-Deep-RL

## Environment Details

In the environment, two agents are trained to play tennis with each other.
If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

The task is episodic, and in order to solve the environment, the agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents).

After each episodes, the agents individual rewards are added up to get a score for each agent respectively. We take the max of these values to get the reference score for the episode.
The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5. *In the provided solution, the threshold for solving the environment was set higher to be sure the results are more stable, with an average score of +0.9 needed over 100 episodes*

The observation space consists of 24 variables corresponding to position, rotation, velocity, etc. Each action for each of the agents consists of two numbers, thus the action vector is of size 2. Every entry in the action vector should be a number between -1 and 1.

## Dependencies

To run the code and train the agent, the dependencies in the ./python folder need to be installed via the command

```
!pip -q install ./python
```

The command, however, is also included into the solution notebook.


Also, the UnityEnvironment package needs to be installed. Detailed instructions can be found [here](https://classroom.udacity.com/nanodegrees/nd893/parts/ec710e48-f1c5-4f1c-82de-39955d168eaa/modules/89b85bd0-0add-4548-bce9-3747eb099e60/lessons/3cf5c0c4-e837-4fe6-8071-489dcdb3ab3e/concepts/e85db55c-5f55-4f54-9b2b-d523569d9276).

## Instructions

The code can be run via the provided "Solutions.ipynb" notebook. The notebook is built consecutively, thus running all cells via the _Cell->Run All_ command will train the agent and display the results.

Note: If the agent should act solely based on the learned weights, it is required though to change the epsilon value to a value close to 0 in order to disable the epsilon-greedy policy accordingly.

## Further files

The trained weights are saved in the "checkpoint" files as a PyTorch state dictionary. In order to load the trained weights and continue training based on those weights, the _retrain_ hyperparameter needs to be set to _True_.
