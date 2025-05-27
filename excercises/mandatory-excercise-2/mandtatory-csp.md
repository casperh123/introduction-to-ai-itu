# Mandatory assignment

In this assignment, we consider binary CSPs where the constraint graph forms a tree. Recall that the nodes
and edges of the constraint graph represent variables and constraints, respectively. As an example consider
the binary CSP W = (X,D,C) where:

X = {x1, x2, x3, x4, x5};

D1 = {1,2,3}, D2 = {5,7,8}, D3 = {1,2,4}, D4 = {0,2,4}, D5 = {1,2};

C = { Cx1x2={(1,7),(2,8) },
 Cx1x5={(1,2),(2,1) },
 Cx2x3={(8,4), (7,2) },
 Cx2x4={(8,0), (8,2), (5,4) } }.

## Reduce the domains of the variables of W such that W becomes arc consistent.

After reducing the domain of the variables, such that the entirety of W is arch consistent, we have the following domains:

- $D_1 = {1, 2}$
- $D_2 = {5, 7, 8}$
- $D_3 = {2, 4}$
- $D_4 = {0, 2 ,4}$
- $D_5 = {1, 2}$

## Write a solution to W.

A solution to the CSP could be:

- $X_1 = 2$
- $X_2 = 8$
- $X_3 = 4$
- $X_4 = 0$
- $X_5 = 1$


## Describe in words a polynomial time algorithm that can find a solution to an 

A CSP like this can be solved by Firsty picking a node to be root, and then tracing through the tree from leaves to root. For each edge, we REVISE to clean up the domains in accordance to the constraints. Once the root is reached, work back down the tree, assigning values to the variables. Pick any valid value for the root, then for each child, choose a value that satisfies it's parent's constraints. Because we already made the graph arc consistent, we will always find a compatible value for each variable without having to backtrack.