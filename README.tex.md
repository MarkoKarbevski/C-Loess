# CLR
Clustered Localised Linear Regression 
Authors: Marko Karbevski (1,2), Petar Jovanovski (2), Viktor Stojkoski (2,3)

Loess is a well-established machine learning algorithm (one can for example see https://github.com/sigvaldm/localreg for an implementation). Unfortunately, its complexity for predicting $k$ outputs out of a dataset of $n$ samples with dimension $p$ is $O(k(p^2n + p^3))$ in case of the exact computation (using matrix inverses), or $O(knpt)$ for a (stochastic) gradient descent, where $t$ is the number of steps needed for the training. This may be one of the reasons for its lack of popularity despite relatively decent results.

Here we propose an alternative approach based on the K-Means clustering method. Namely, first we run the K-Means clustering algorithm to obtain $k$ clusters, where $k$ is a tuneable parameter specified by the user. Next, for each centroid, we train a weighted least squares linear regression model. The weights are inversely proportional to the distance from the given centroid, as in the case of loess. Finally, for a given input $x$, we find the closest centroid and its corresponding model and compute the output from there.

When it comes to classification, one can replace linear regression with the logistic regression. Everything else remains the same.





(1) Sorsix International
(2) Macedonian Academy of Sciences & Arts
(3) Faculty of Economics, Ss. Cyril and Methodius University in Skopje
