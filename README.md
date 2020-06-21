# CLR - Clustered Localised Linear Regression (UNDER CONSTRUCTION!)

Authors: Marko Karbevski (1,2), Petar Jovanovski (2), Viktor Stojkoski (2,3)

Loess is a well-established machine learning algorithm (one can for example see https://github.com/sigvaldm/localreg for an implementation). Unfortunately, its complexity for predicting <img src="/tex/63bb9849783d01d91403bc9a5fea12a2.svg?invert_in_darkmode&sanitize=true" align=middle width=9.075367949999992pt height=22.831056599999986pt/> outputs out of a dataset of <img src="/tex/55a049b8f161ae7cfeb0197d75aff967.svg?invert_in_darkmode&sanitize=true" align=middle width=9.86687624999999pt height=14.15524440000002pt/> samples with dimension <img src="/tex/2ec6e630f199f589a2402fdf3e0289d5.svg?invert_in_darkmode&sanitize=true" align=middle width=8.270567249999992pt height=14.15524440000002pt/> is <img src="/tex/d8fe06ebc8b29036cbb5a50ccd417a5d.svg?invert_in_darkmode&sanitize=true" align=middle width=108.88977494999999pt height=26.76175259999998pt/> in case of the exact computation (using matrix inverses), or <img src="/tex/c09acd2fb583f905bea6ff7443777c45.svg?invert_in_darkmode&sanitize=true" align=middle width=58.92976154999999pt height=24.65753399999998pt/> for a (stochastic) gradient descent, where <img src="/tex/4f4f4e395762a3af4575de74c019ebb5.svg?invert_in_darkmode&sanitize=true" align=middle width=5.936097749999991pt height=20.221802699999984pt/> is the number of steps needed for the training. This may be one of the reasons for its lack of popularity despite relatively decent results.

For the sake of curiosity, we investigate an alternative approach based on the K-Means clustering method. Namely, first we run the K-Means clustering algorithm to obtain <img src="/tex/63bb9849783d01d91403bc9a5fea12a2.svg?invert_in_darkmode&sanitize=true" align=middle width=9.075367949999992pt height=22.831056599999986pt/> clusters, where <img src="/tex/63bb9849783d01d91403bc9a5fea12a2.svg?invert_in_darkmode&sanitize=true" align=middle width=9.075367949999992pt height=22.831056599999986pt/> is a tuneable parameter specified by the user. Next, for each centroid, we train a weighted least squares linear regression model. The weights are inversely proportional to the distance from the given centroid, as in the case of loess. Finally, for a given input <img src="/tex/332cc365a4987aacce0ead01b8bdcc0b.svg?invert_in_darkmode&sanitize=true" align=middle width=9.39498779999999pt height=14.15524440000002pt/>, we find the closest centroid and its corresponding model and compute the output from there.

When it comes to classification, one can replace linear regression with the logistic regression. Everything else remains the same.





(1) Sorsix International

(2) Macedonian Academy of Sciences & Arts

(3) Faculty of Economics, Ss. Cyril and Methodius University in Skopje
