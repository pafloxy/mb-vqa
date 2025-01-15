---
type: "[[_tags/_notetype_tags/*idea-note]]"
people:
  - "[[_tags/_people/@harold|@harold]]"
---
## note-outline 

- stabilizer groups 
    - defn. [[ReadingDocuments/StabGroundStatesSimManyBodyPhysics@JSun24.pdf#page=2&selection=99,0,101,58|StabGroundStatesSimManyBodyPhysics@JSun24, p.2]]
    - properties 
    - examples 
- stabilizer hamiltonians 
    - defn [[ReadingDocuments/StabGroundStatesSimManyBodyPhysics@JSun24.pdf#page=3&selection=3,0,5,48|StabGroundStatesSimManyBodyPhysics@JSun24, p.3]]
    - examples 
        - toric-code 
        - graph-code 
    - properties 
        - some properties are mentioned already in the refs
        - [x] add to note the properties about degeneracy of the eigenspectrum of a general stabilizer hamiltonian , and ho that related to the logical space of the corresponding stabilizer code .
        - [x] action of paulis and pauli-exponentials on stabilizer-hamiltonians (ref. [[notes/mbqc-vqe/mbqc-vqe-v0.1|mbqc-vqe-v0.1]]) 
            - [ ] or [[notes/mbqc-vqe/mbqc-vqe-v0.2#^67a5f5|perturbative analysis on stabilizer hamiltonians]] ?
        - [ ] should we include [[notes/mbqc-vqe/TrackingStabilizerStates-under-PauliExponentiation|TrackingStabilizerStates-under-PauliExponentiation]] ? 
### [[dailynotes/09-01-2025|09-01-2025]]

- make all the sections and subsections of that the skeleton of the document is fixed from the beginning 
- for the sections on which extensive literature is already available insert the references directly under the section titles instead of putting it in the note. for eg. 
    - stabilizer groups 
    - basic structure and examples of stabilizer hamiltonians 
- [ ] deciding to elaborate the main ideas using the example on bell-states, i'll also introduce the idea of logical operators 

### [[dailynotes/14-01-2025|14-01-2025]]

- https://arxiv.org/pdf/1505.07811 ; Section: SUPPLEMENTAL MATERIAL, Stabilizer heat bath and Davis generators.
    - Has some description on the notation thta t ackles the action of paulis on stabilizer hamiltonians
    - ![[obsidian-attatchments/Pasted image 20250114181904.png]]
- [ ] we also need to include the behavior under the action of pauli-exponentials as well.
- [ ] I think we also need to present the case where we have $k\leq n$ generators, which is something excluded in the usual literature but is rather important for our line of study.

### [[dailynotes/15-01-2025|15-01-2025]]

- [ ] Need to find a better way to render the notes
    - Rendering on git is bad but shows up pretty well on VSCoded .md rendering
        - isseu rendering multiline math.
    - [x] set up another branch on the repo `pretty-rendering` dedicated to this..
    - Tried rendering latex and direct pdf, 
        - math is okay but issues with comments, not very visual.
        - **i think its better to be .md than pdf.**
        - 