# sonnet-generation
This project attempts to generate Shakespearean sonnets using a hidden markov model.

An HMM learns patterns in text by identifying the underlying probabilistic structure of data and using that structure to generate new data. During training, the model learns the probabilities of transitioning from one state to another and the probabilities of emitting each word at each state. These probabilities are stored in the transition and observation matrices. This is done using the Baum-Welch algorithm which iterates between running Forward-Backward to compute marginal probabilities based on the current model pa- rameters, and updates the model parameters (observation and transition matrices) based on the maximium likelihood estimate until convergence. In other words, the model learns what words correspond to which states, and the order that states usually appear in.

Once the HMM is trained, it can be used to generate new sequences of text by choosing a random starting word(or ending rhyme in our case), and iteratively choosing the next state and word with highest likeli- hood based on the learned transition and observation matrices.

In terms of actually training the model, training it with more states and more iterations makes the sonnets much more cohesive and Shakespearean-sounding. Note that the way HMMs work is that it continuously generates the next word from the previous word — thus, there is no cohesive topic as of now.

For example, here is an example sonnet generated with 30 states and 100 iterations:

Me fears beauty and the roses of noon,
With my blanks mind or what i wouldst in pen,
O’er-snowed had not when my grown to live of son,
Attending fleet’st it and in me though of men.

Of beauty and will reasons memory,
Compared nor her and and do I either face,
Or when days to beauty eternity,
Nor hearts falsely ground couplement give place.

Equal love speaking as gone poverty,
And like a that not of more that new thee,
Older for to absence of injury,
’oncord i will thee things of melancholy.

Kingdoms or nothing of not the world’s of give,
Grief and suffered and thee yet mine right live.
