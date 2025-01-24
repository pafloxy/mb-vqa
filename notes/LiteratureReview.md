
> [rp]  Here I'm including some of the papers that would be relevant for you when you are initiating the project, mainly they're classified into papers that are look into properties of Stabilizer Hamiltonians, and those that are more about using MBQC to solve VQA over stabilizer hamiltonians. To each entry i have put a number of stars (`*`>`**`>`***`) to indicate how important it might be, however its just my preference and you're free to ignore it :) 

> [rp|22-01-25]  In the section [MBQC based VQE](###MBQC based VQE), you will see that we have certain bias toward the examples where its about Stabilizer Hamiltonians than to other physically relevant ground-state finding problems. This stems from the observation that since MBQC is natively using the properties of the stabilizers to facilitate the entire computation, its way more convenient to mathematically analyse the effect of the ansatz in terms of its computational effects on the eigen-specturm of the stabilizer hamiltonian. 
> However, if you think there might be some ways of analysing the non stabilizer hamiltonian cases do let us know. None of me or harold have spent enough time in looking at those cases, so its likely we missed something interesting :)


---

- The analysis of Stabilizer Hamiltonians under perturbation is often studied as a phase-transition problem, i.e in presence of significant perturbation to the ground-state loses the geometric structure imposed via the graph-state (aka. topological phase). Most of the papers with numerical experimentation based on this will involve this fact in one way or the other.
- You will find that the 'Toric-Code' is often used as the case to analyse in the references, you can have a nice introduction to it here https://arthurpesah.me/blog/2023-05-13-surface-code/.


### Variational Algorithms 
- [VQMcer20](https://arxiv.org/abs/2012.09265) `*`
    - Introduces and summarizes the basic concepts of variational quantum algorithms, among which the Variational Quantum Eigensolver (VQE) is of our key interest.
- [VQJtil21](https://arxiv.org/abs/2111.05176) `**`
    - (Too BIG :/, book like) Summarizes existing methodology regarding VQE.

### Stabilizer Hamiltonians 

- [DSSLeo24][https://arxiv.org/pdf/2403.14912]  `***` 
    - We liked that it provides a rigorous way to analyze partially (doped) stabilizer states and mentions some nice properties about the eigen-spectrum of the perturbed hamiltonian. 
    - They also mention an algorithm that could help sample the gibbs-distribution, which is quite intuitive 
    - However, we don't think their methods are super useful under practical situations. The numerical cases they have analysed aren't too convincing of their capabilities either. 

### Clifford Ansatz

- [CAPlov22](https://arxiv.org/abs/2202.12924) `*`
    - Here the authors aim to find ansatz that are clifford. (Clifford unitaries are simulatable classically by the Gottessman-Knill theorem)
    - Usually most variational algorithms in the literature are non-clifford because the variational angles are allowed to vary continuously, whereas restricting them to clifford would require us to vary only over a discrete set of angles combined with the fact that its classically simulatable makes their approach a bit "out-of-the-box" which is why we found it interesting.


### MBQC based VQE

-  [VMLdel21](http://arxiv.org/abs/2010.13940v3)  `*`
    - This is the primary paper that talked about construction of "Graph-decoration" as a techniques that allows us to construct an variational ansatz out of a graph-state. In essence this is very similar to the construction of variational unitaries except here we are doing it in the MBQC model. 
    - Though the introduce interesting concepts, they do little in explicating their choice of doing the decoration. Nor do they provide explicit methods to construct such ansatz in a general setting. **It was in fact in our desire to design more general ansatz that led us to work on designing an algorithm, that would help us generate graphs on which MBQC can be run 'deterministically', we will refer to this algorithm as [PGA]** 
    - The numerical evidence they provide are pretty convincing, though there examples are pretty restricted.
        - One of there examples was about 'finding ground state of perturbed Toric Code', which is a key case to analyse in our study of Ground State of Perturbed Stabilizer Hamiltonian. 
        - The other example does not involve Stabilizer Hamiltonians, and we found it a bit difficult to analyze theoretically using the set of tools that we have. Besides our version of ansatz design (i.e PGA) is not super useful in the context of non-stabilizer hamiltonian. 
- [VMLdel23](https://arxiv.org/abs/2305.19200) `**`
    - Similar paper as before but they discuss a wide variety of problems which are more physically relevant
    - This time there techniques have minimal relevance to the case of stabilizer hamiltonians.
- [DAAsch23](http://arxiv.org/abs/2312.13241) `**`
    - Improvisations upon the decorations that were discussed in [VMLdel21], but still lacks on generalizability for other problems.