# Learning Algorithm  

In this project, I choose [DDPG](https://arxiv.org/pdf/1509.02971.pdf) as the model to solve the environment. In DDPG, there are four Deep Neural Netowrks working together to perform the training and inference. An Actor model (Regular and Target) and a Critic model (Regular and Target). The Actor and Critic models' architecture are almost identical as follows: 

## Actor (for both Regular and Target)
        RELU (33 to 400)                        RELU (400 to 300)                               Tanh
State (33) -------> Fully Connected Layer 1 (400 units) -------> Fully Connected Layer 2 (300 units) -------> Action

## Critic (for both Regular and Target)

        RELU (33 to 400)                          RELU (400 + 33 to 300)                            Tanh
State (33) -------> Fully Connected Layer 1 (400 + 33 units) -------> Fully Connected Layer 2 (300 units) -------> Action

**RELU:** Activation Functin applied.  
**Tanh:** Tangent Activation Function applied because the action space is continuous between -1 to 1.  


## Reply Buffer
Although DDPG is claimed as an Actor-Critic approach in the paper, however, it also looks like DQN method because the **Reply Buffer** is used.  

## Soft Update Strategy
Unlike DQN where the Target Network weights are updates only every 10K timesteps (a big update after a certain time), DDPG uses Soft Update that updates the Target Network weights gradually (every timestep) by mixing the Regualr Network weights (99.99%) to the Target Network weights (0.01%).  

## Ornstein-Uhlenbeck process
In Actor Regular Network, a noise is introduced when predciting the best belived action. I noticed that the original implementation in [Udacity Repository HERE](https://github.com/udacity/deep-reinforcement-learning/blob/master/ddpg-pendulum/ddpg_agent.py) is not in the right way. Initially, the learning progress went too slow (3 score after 500 epoches) by using the original implementation. Afterwards, I changed it to use standard normal distrubution by using action size and achieved 30+ within 502 epoches, please refer to ddpg_agent.py for further details.

# Hyper Parameters
| Parameter | Value | Context | Description | 
| -------- | -------- | -------- | -------- |
| BUFFER_SIZE | 1e6 | Reply Buffer | Reply Buffer size |
| BATCH_SIZE  | 1024 | Reply Buffer | The size of collected experience that us enough to start using Reply buffer for learning |
| GAMMA | 0.99 | Critic | Discount factor | 
| TAU | 1e-3 | Both Actor and Critic | For soft update of target parameters | 
| LR_ACTOR | 1e-3 | Actor | Learning rate of the Actor |
| LR_CRITIC | 1e-3 | Critic | Learning rate of the Critic |
| WEIGHT_DECAY | 0 | Critic | L2 weight decay used in Critic optimizer | 
| UPDATE_EVERY | 20 | Both Actor and Critic | The time steps that the actor and critic networks use to update the Target Network weights |


# Plot of Rewards
I choose the **Single Agent** approach to solve the environment to reach 30+ scores within 502 epoches. Here is the plot: 
<img width="488" alt="Round2 Training Result" src="https://github.com/Ryan-ZL-Lin/RLND-Continuous_Control/assets/33056320/81c9a02f-2a2e-4eb7-8151-541e0e3ab5b5">

The checkpoints are saved in **checkpoint_actor_single.pth** and **checkpoint_critic_single.pth** for both Actor and Critic model accordingly.

# Ideas for Furture Works
- To solve the environment by using **20 Agents** approach.
- To solve the environment by using [PPO(Proximal Policy Optimization)](https://arxiv.org/abs/1707.06347).

