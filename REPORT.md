[//]: # (Image References)

[image1]: https://raw.githubusercontent.com/fredericosantos/DRLN_Navigation/master/image1.png "Random Samples"
[image2]: https://raw.githubusercontent.com/fredericosantos/DRLN_Navigation/master/image2.png "Random batches of Samples"

# Report on Project 1: Navigation

## Learning Algorithm

### Learning Algorithm

I used the standard DQN Agent for this project. I used the recently released Rectified Adam as my optimizer.

### Hyperparameters

The hyperparameters I chose for this particular agent were:

- Buffer size (buffer_size): int(1e5)
- Batch Size (batch_size): 128
- Discount factor (gamma): 0.99
- Soft update of target parameters (tau): 1e-3
- How many steps it takes to update the network (update_every): 4
- Epsilon starting value (eps_start): 1.0
- Epsilon decay (eps_decay): 0.96
- Epsilon minimum value (eps_end): 0.01
- Maximum steps to take during an episode (max_t): 1000
- Learning rate (lr) = 1e-5

I've found that setting the epsilon decay to 0.96 improved the agent's learning time the most.

### Model Architecture

I built a neural network with 2 hidden layers with 2048 hidden neurons, with each layer being activated by the ReLU function except for the final layer.

## Plot of Rewards

Using a replay buffer that randomly samples from the experiences memory, the agent was able to solve the environment in 383 steps.

![Random loose samples][image1]

Using a replay buffer that randomly selects 2 batches of experiences next to each other, the agent was able to solve the enviroment in 380 steps.

![Random batches of samples][image2]

It appears that my idea to pick experiences that were close to each other did not have a significant change in the agent's performance to achieve a score of 13.

## Ideas for Future Work

In the future I would like to be able to implement the Double DQN algorithm with a working Prioritized Experience Replay. I would also improve the agent's performance by adding a dueling DQN.

I'd also like to challenge the method to store experiences in memory as currently it's simply keeping the latest experiences.






