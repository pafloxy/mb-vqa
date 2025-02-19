[2025-02-07 Fri]
================

# Reviewing Stabilizer formalism / properties + GK theorem


# Next steps


## Understanding the tools to compare solutions

-   We want to compare our method to others.
-   This means we need to think about tools / techniques to compare results. The "doped stabilizer state paper" seems to be doing it but we need to understand how costly (in terms of classical computation) it is to actually compare ourselves to the exact (numerical) simulation. Can the evaluation of an order parameter be lowering the cost? or is it anyways the same as computing the full exact ground state?
-   On the same paper, what would happen if we add a second location where there is a defect? Does it make it harder to simulate classically or not?
-   Are there classical approximate solutions that we could use? (like some package performing MPS or Tensor product states).
-   May be the same situation holds for other papers. It would be nice to have a clear view of how to compare our solution to theirs and how resource hungry it is.


## Summarizing the various problems at hand

-   Define what is the problem that is proposed.
-   What needs to be done to simulate the "baseline" solution (ie either exact classical simulation or something else) and what it needs to be done.
-   Trying to understand what we need to do on our side to simulate.
