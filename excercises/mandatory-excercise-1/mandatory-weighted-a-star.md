# Weighted A*

Let WEIGHTED A* denote A* using the evaluation function $f(n) = (1-w)g(n) + wh(n)$, where $0 ≤ w ≤ 14$ and $h(n)$ is admissible.

### Question A

Which algorithm does WEIGHTED A* correspond to with w = 1 and w = 0.5, respectively?

#### Answer

The function 

$f(n) = (1-w)g(n) + wh(n)$

With the weight $W = 0$

$(1 - 0) * g(n) + 0 * h(n)$

Can be reduced to 

$ 1 * g(n)$

$g(n)$

**Which is equivalent to a Uniform Cost search: $f(n) = g(n)$**

With weight $W = 0.5$

$(1 - 0.5) * g(n) + 0.5 * h(n)$

The function can be reduced to

$0.5 * g(n) + 0.5 * h(n)$

Since we know that the heuristic is admissable, we know that

$0.5 * h(n) \leq 0.5 * g(n) $

**Which is equivalent to regular A\*: $f(n) = g(n) + h(n)$**

### Question B

For which values of w are WEIGHTED A* optimal (Assuming that A* only is optimal if it uses an admissible heuristic)?

#### Answer

With an admissable heuristic, we are certain that ***Weighted A*** will find the optimal path for all $W$, where $0 \leq W \leq 1$. This is due to the fact, that for all weights between $0$ and $1$, an admissable heuristic $h(n)$ will at most be $1 * h(n)$ which is $h(n)$. Since the heuristic is admissable, we know that $h(n)$ is **at most** the cost of reaching the goal. Since the heuristic is not overestimating the cost of reaching the goal, the algorithm will always find the optimal path.
