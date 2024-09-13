
This research aims to expand the algorithmic capability for tasking sensors to investigate human-specified hypotheses about space objects (SOs).
The goal is to improve the ability to evaluate internal- and physical- state hypotheses in cases where there are many objects and a collection of sensors with diverse capabilities.


<!-- **Problem Description** -->
<!-- Describe the problem of catalog maintenance and hypothesis resolution -->


**Technical Approach**
The approach can be broken down into two main steps:
1. Generating a base plan using integer linear programming
2. Generating a refined MCTS plan accounting for the object of interest


### 1) Integer Linear Program
The base integer linear programming approach aims to judiciously allocate sensors to space objects in a manner where the severity of the worst-case scenario is minimized. 

Formally, the ILP is given by
<!-- <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script> -->
$$
\begin{aligned}
\text{maximize} \quad & t \\
\text{subject to} \quad & X_{ijt} \in \{0,1\}^{I\times J \times T} \\
& X_{ijt} \preceq O \\
& t \preceq \sum_{j,t} X_{ijt} \\
& \sum_{i} X_{ijt} \preceq 1 \, .
\end{aligned}
$$

Here $$X_{ijt}$$ is a binary 3-dimensional control variable representing whether or not observer $$j$$ observers object $$i$$ at time step $$t$$, and $$O_{ijt}$$ represents whether or not observer $$j$$ *is able to* observe object $$i$$ at time $$t$$.

For ground based-sensors, the ILP plan can be visualized as follows:
![ILP-Plan](../assets/images/ilp-plan-600.gif)
.

### 2) Monte Carlo Tree Search
Building on the ILP solution as a baseline, we assume the existence of an object of interest in the catalogue, for which we seek to resolve a specific hypothesis. This work focuses on determining the drag configuration for the object in question. To achieve this, we use Monte Carlo Tree Search (MCTS) applied to a belief Markov Decision Process (MDP). The goal of the MCTS solver is to minimize the entropy of the distribution over possible hypotheses while minimally disrupting the baseline catalogue maintenance plan.
