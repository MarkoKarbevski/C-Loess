# CLR
Localised linear regression python code

Loess is a well-established machine learning algorithm. Unfortunately, its complexity for predicting $k$ outputs out of a dataset of $n$ samples with dimension $p$ is $`O(k(p^2n + p^3))`$ in case of the exact computation (using matrix inverses), or $O(knpt)$ for a (stochastic) gradient descent, where $t$ is the number of steps needed for the training. 
