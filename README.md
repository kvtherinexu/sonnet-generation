# sonnet-generation
This project attempts to generate Shakespearean sonnets using a hidden markov model.

An HMM learns patterns in text by identifying the underlying probabilistic structure of data and using that structure to generate new data. During training, the model learns the probabilities of transitioning from one state to another and the probabilities of emitting each word at each state. These probabilities are stored in the transition and observation matrices. This is done using the Baum-Welch algorithm which iterates between running Forward-Backward to compute marginal probabilities based on the current model pa- rameters, and updates the model parameters (observation and transition matrices) based on the maximium likelihood estimate until convergence. In other words, the model learns what words correspond to which states, and the order that states usually appear in.

Once the HMM is trained, it can be used to generate new sequences of text by choosing a random starting word(or ending rhyme in our case), and iteratively choosing the next state and word with highest likeli- hood based on the learned transition and observation matrices.

In terms of actually training the model, training it with more states and more iterations makes the sonnets much more cohesive and Shakespearean-sounding. Note that the way HMMs work is that it continuously generates the next word from the previous word — thus, there is no cohesive topic as of now.
