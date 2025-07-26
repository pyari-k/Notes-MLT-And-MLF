# Week 1 - Machine Learning Techniques

## Supervised Learning 
    * Regression - eg: prediction of house rents and prices
    * Classification - eg: spam classifier 
    * Ranking
note: labels are also available

## Unsupervised Learning 
    * Clustering 
    * Representation learning 

Week 1 is about representation learning

## What is Representation Learning: 
If all the data points lie on the same line, then, the entire data can be represented using a representative vector or point and a set of coefficients. This also helps compress the data. 

If one or more of the points, say x, do not fall on the line, the point can be projected on to the line with an error. 

That way, the point of projection is cW, where c is the coefficient and W is the vector or line on which the point, x is projected. 

Then, the projection of x can be calcuated as: $(\frac{x \cdot w}{|w|^2}) \cdot w$

## Error:
$error = x_{i} - projection(x)$ 

## Minimising the error
Minimising the error is found to be equivalent to maximising $W \cdot C \cdot W^T such $|w| = 1$ 


It is also found that W is maximised when W is the eigen vector corresponding to the largest eigen value of the covariance matrix