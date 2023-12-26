# Learning Algorithm  

In this project, I choose DDPG as the model to complete solve the environment. in DDPG, there 2 two neural netowrks are working together to do the training and inference. An Actor model and a Critic model. The two models' architecture are almost identical as follows: 

**RELU:** Activation Functin applied.  
**Tanh:** Tangent Activation Function applied because the action space is continuous between -1 to 1.

## Actor
        RELU (33 to 400)                        RELU (400 to 300)                               Tanh
State (33) -------> Fully Connected Layer 1 (400 units) -------> Fully Connected Layer 2 (300 units) -------> Action

## Critic

        RELU (33 to 400)                          RELU (400 + 33 to 300)                            Tanh
State (33) -------> Fully Connected Layer 1 (400 + 33 units) -------> Fully Connected Layer 2 (300 units) -------> Action
