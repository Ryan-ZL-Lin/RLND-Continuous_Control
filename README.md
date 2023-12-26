# RLND-Continuous_Control

## The Environment Introduction

### Unity ML-Agent
Unity Machine Learning Agents (ML-Agents) is an open-source Unity plugin that enables games and simulations to serve as environments for training intelligent agents.

For game developers, these trained agents can be used for multiple purposes, including controlling NPC behavior (in a variety of settings such as multi-agent and adversarial), automated testing of game builds and evaluating different game design decisions pre-release.

In this course, you will use Unity's rich environments to design, train, and evaluate your own deep reinforcement learning algorithms. You can read more about ML-Agents by perusing the [GitHub repository](https://github.com/Unity-Technologies/ml-agents)

Note: The Unity ML-Agent team frequently releases updated versions of their environment. We are using the v0.4 interface. To avoid any confusion, please use the workspace we provide here or work with v0.4 locally.

For this project, I work with the Reacher environment.

![Unity_Reacher_Env](https://github.com/Ryan-ZL-Lin/RLND-Continuous_Control/assets/33056320/b6a17b34-4bd4-44c9-a863-db0b9b4893c9)

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

**Discrete State Space (33)**  
The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. 

**(Continuous Action Space)**  
Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.


## Environment Setup

**Step 1: Activate the Environment**  
If you haven't already, please follow the instructions in the [DRLND GitHub repository](https://github.com/udacity/deep-reinforcement-learning#dependencies) to set up your Python environment. These instructions can be found in README.md at the root of the repository. By following these instructions, you will install PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.

(For Windows users) The ML-Agents toolkit supports Windows 10. While it might be possible to run the ML-Agents toolkit using other versions of Windows, it has not been tested on other versions. Furthermore, the ML-Agents toolkit has not been tested on a Windows VM such as Bootcamp or Parallels.

**Step 2: Download the Unity Environment**  
For this project, you will not need to install Unity - this is because we have already built the environment for you, and you can download it from one of the links below. You need only select the environment that matches your operating system:

**Version 1: One (1) Agent**
- Linux: click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
- Mac OSX: click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
- Windows (32-bit): click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
- Windows (64-bit): click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

**Version 2: Twenty (20) Agents**
- Linux: click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
- Mac OSX: click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
- Windows (32-bit): click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
- Windows (64-bit): click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)

Then, place the file in the p2_continuous-control/ folder in the DRLND GitHub repository, and unzip (or decompress) the file.

(For Windows users) Check out this link if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

(For AWS) If you'd like to train the agent on AWS (and have not enabled a virtual screen), then please use this link (version 1) or this link (version 2) to obtain the "headless" version of the environment. You will not be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (To watch the agent, you should follow the instructions to enable a virtual screen, and then download the environment for the Linux operating system above.)

**Step 3: Explore the Environment**  
After you have followed the instructions above, open Continuous_Control.ipynb (located in the p2_continuous-control/ folder in the DRLND GitHub repository) and follow the instructions to learn how to use the Python API to control the agent.



## Solving the Environment  
In this project, I chose the first version, which is the "single agent approach" by using **DDPG (Deep Determministic Policy Gradient)** to solve the environment.
Instaed of doing this on my local environment, I used Udacity Worksapce to complete the project.
The environment is considered solved by reach average 30+ score within 1000 epoches.

## Instructions
Open the **Continuous_Control.ipynb** and go through each cell to download the dependicies and train the model. Please note that **step 3 - Take Random Actions in the Environment** is for infomration only, which can be skipped.

