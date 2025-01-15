
> [rp]  Here I'm including some of the papers that would be relevant for you when you are initiating the project, mainly they're classified into papers that are look into properties of Stabilizer Hamiltonians, and those that are more about using MBQC to solve VQA over stabilizer hamiltonians. To each entry i have put a number of stars (`*`,`**`,`***`) to indicate how important it might be, however its just my preference and you're free to ignore it :) 

- The analysis of Stabilizer Hamiltonians under perturbation is often studied as a phase-transition problem, i.e in presence of significant perturbation the the ground-state loses the geometric structure imposed via the graph-state (aka. topological phase). Most of the papers with numerical experimentation based on this will involve this fact in one way or the other.
- You will find that the 'Toric Code' is often used as the case to analyse in the references, you can have a nice introduction to it here https://arthurpesah.me/blog/2023-05-13-surface-code/.

### Stabilizer Hamiltonians 

- [DSSLeo24][https://arxiv.org/pdf/2403.14912] 
    - We liked that the fact that it provides a rigorous way to analyze partially (doped) stabilizer states and mentions some nice properties about the eigen-spectrum of the perturbed hamiltonian. 
    - They also mention an algorithm that could help sample the gibbs-distribution, which is quite intuitive 
    - However, we don't think their methods are super useful under practical situations. The numerical cases they have analysed aren't too convincing of their capabilities either. 
- 

### MBQC  based VQE