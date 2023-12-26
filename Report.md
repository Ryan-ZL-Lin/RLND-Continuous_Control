# Learning Algorithm  

In this project, I choose [DDPG](https://arxiv.org/pdf/1509.02971.pdf) as the model to solve the environment. In DDPG, there are two Deep Neural Netowrks working together to perform the training and inference. An Actor model and a Critic model. The two models' architecture are almost identical as follows: 

**RELU:** Activation Functin applied.  
**Tanh:** Tangent Activation Function applied because the action space is continuous between -1 to 1.

## Actor
        RELU (33 to 400)                        RELU (400 to 300)                               Tanh
State (33) -------> Fully Connected Layer 1 (400 units) -------> Fully Connected Layer 2 (300 units) -------> Action

## Critic

        RELU (33 to 400)                          RELU (400 + 33 to 300)                            Tanh
State (33) -------> Fully Connected Layer 1 (400 + 33 units) -------> Fully Connected Layer 2 (300 units) -------> Action

**Reply Buffer**
Although DDPG is claimed as an Actor-Critic approach in the paper, however, it also looks like DQN method because the **Reply Buffer** is used.

**Soft Update**  
