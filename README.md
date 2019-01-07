# NeurIPS2018-Challenge-RL-for-Prosthetics

In this competition, you are tasked with developing a controller to enable a physiologically-based human model with a prosthetic leg to walk and run.
In this repo, we are trying to apply Reinforcement Learning (RL) to enable prosthetics to calibrate with differences between humans and differences between walking environments. using [OpenSim](https://opensim.stanford.edu/) to simulate prosthetic.

[![AI for prosthetics](https://s3-eu-west-1.amazonaws.com/kidzinski/nips-challenge/images/ai-prosthetics.jpg)](https://github.com/stanfordnmbl/osim-rl)

## Objectives
1- Benchmarking RL algorithms Deterministic Policy Gradient [DDPG](https://arxiv.org/abs/1509.02971), Trust Region Policy Optimization [TRPO](http://proceedings.mlr.press/v37/schulman15.pdf) and Proximal Policy Optimization [PPO](https://arxiv.org/abs/1707.06347) algorithms.

2- Reduce training time using Imitation Learning algorithm Dataset Aggregation algorithm [DAgger](http://proceedings.mlr.press/v15/ross11a/ross11a.pdf).

3- Modificat DAgger algorithm to balance between exploration and exploiting.

## Algorithms and Hyperparameters
- [DDPG](https://arxiv.org/abs/1509.02971) is a model-free, off-policy actor-critic algorithm using deep function approximators that can learn policies in high-dimensional, continuous action spaces.DDPG is based on the deterministic policy gradient (DPG) algorithm. it combines the actor-critic approach with insights from the recent success of Deep Q Network (DQN).

- [PPO](https://arxiv.org/abs/1707.06347) is a policy optimization method that use multiple epochs of stochastic gradient ascent to perform each policy update.

- [TRPO](http://proceedings.mlr.press/v37/schulman15.pdf) is a model free, on-policy optimization method that effective for optimizing large nonlinear policies such as neural networks.

## Results

## Discussion

1- OpenSim ProstheticsEnv is a very complex environment, it contains more than 158 continuous state variables and 19 continuous action variables.

2- RL algorithms take a long time to build a complex policy which has the ability to compute all state variables and select action variables which will maximize the reward.

3-[DDPG](https://arxiv.org/abs/1509.02971) algorithm achieves good reward because it designed for high dimensions continuous space environments and it uses the replay buffer.

4- [PPO](https://arxiv.org/abs/1707.06347) the least training time comparing to [DDPG](https://arxiv.org/abs/1509.02971) and [TRPO](http://proceedings.mlr.press/v37/schulman15.pdf) because [PPO](https://arxiv.org/abs/1707.06347) uses gradient algorithm approximation instance of the conjugate gradient algorithm.

5- [TRPO](http://proceedings.mlr.press/v37/schulman15.pdf) algorithm achieved the maximum Reward because it takes time to reach the “trusted” region so it slower than [DDPG](https://arxiv.org/abs/1509.02971) and [PPO](https://arxiv.org/abs/1707.06347) .


## Limitations

1- The prosthetic model can not walk for large distances.

2- Each experiment runs for one time, So we are planing to Repeat each experiment number of times and take the average.

3- We used common hyperparameters for all algorithm to make benchmarking between algorithms, we need to select the best hyperparameters for each algorithm and environment.

4- We benchmarcked three RL algorithms only and from one library ([ChainerRL](https://github.com/chainer/chainerrl)).

5- We transfer learning between similar agents.


## Getting Started
### ChainerRL libary
[ChainerRL](https://github.com/chainer/chainerrl) is a deep reinforcement learning library that implements various state-of-the-art deep reinforcement algorithms in Python using Chainer, a flexible deep learning framework.

ChainerRL contains DQN, DDPG, TRPO, PPO, etc Reinforcment Learning algorithms.

### Environment
To model physics and biomechanics we use [OpenSim](https://github.com/opensim-org/opensim-core) - a biomechanical physics environment for musculoskeletal simulations.

### Installing
Install OpenSim Envirnment 
```
conda create -n opensim-rl -c kidzik opensim python=3.6.1
source activate opensim-rl
```
Install ChainerRL libary
```
pip install chainerrl
```

