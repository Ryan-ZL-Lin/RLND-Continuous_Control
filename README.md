# RLND-Continuous_Control

## The Environment

### Unity ML-Agent
Unity Machine Learning Agents (ML-Agents) is an open-source Unity plugin that enables games and simulations to serve as environments for training intelligent agents.

For game developers, these trained agents can be used for multiple purposes, including controlling NPC behavior (in a variety of settings such as multi-agent and adversarial), automated testing of game builds and evaluating different game design decisions pre-release.

In this course, you will use Unity's rich environments to design, train, and evaluate your own deep reinforcement learning algorithms. You can read more about ML-Agents by perusing the [GitHub repository](https://github.com/Unity-Technologies/ml-agents)

Note: The Unity ML-Agent team frequently releases updated versions of their environment. We are using the v0.4 interface. To avoid any confusion, please use the workspace we provide here or work with v0.4 locally.

For this project, I work with the Reacher environment.

![Unity_Reacher_Env](https://github.com/Ryan-ZL-Lin/RLND-Continuous_Control/assets/33056320/b6a17b34-4bd4-44c9-a863-db0b9b4893c9)

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.
