# Learning Algorithm  

In this project, I choose [DDPG](https://arxiv.org/pdf/1509.02971.pdf) as the model to solve the environment. In DDPG, there are four Deep Neural Netowrks working together to perform the training and inference. An Actor model (Regular and Target) and a Critic model (Regular and Target). The Actor and Critic models' architecture are almost identical as follows: 

**RELU:** Activation Functin applied.  
**Tanh:** Tangent Activation Function applied because the action space is continuous between -1 to 1.

## Actor (for both Regular and Target)
        RELU (33 to 400)                        RELU (400 to 300)                               Tanh
State (33) -------> Fully Connected Layer 1 (400 units) -------> Fully Connected Layer 2 (300 units) -------> Action

## Critic (for both Regular and Target)

        RELU (33 to 400)                          RELU (400 + 33 to 300)                            Tanh
State (33) -------> Fully Connected Layer 1 (400 + 33 units) -------> Fully Connected Layer 2 (300 units) -------> Action

**Reply Buffer**
Although DDPG is claimed as an Actor-Critic approach in the paper, however, it also looks like DQN method because the **Reply Buffer** is used.

**Soft Update Strategy**  
Unlike DQN where the Target Network weights are updates only every 10K timesteps (a big update after a certain time), DDPG uses Soft Update that updates the Target Network weights gradually (every timestep) by blending the Regualr Network weights (99.99%) with Target Network weights (0.01%)

