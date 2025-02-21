---
type: "[[_tags/_notetype_tags/*formal-note|*formal-note]]"
people:
  - "[[_tags/_people/@martina.leonetti|@martina.leonetti]]"
---
*Here I am summarising some of the rules that we discussed about extracting pauli-exponentials out of measurement pattern. The man idea follows from ther analysis presented in [RMWsim21] (cf. [LiteratureReview](LiteratureReview)), but I have eased up the formalism to suit our specific requirements some of which I disucssed with you.*

---
## Algebraic Identities

### Projectors 
Usually projectors are linear-operators that map a state to a certain subspace. In our work we are usually interested in projectors that map to eigenspaces of multi-qubit pauli operators. 
Given a $n$-qubit pauli $A \in \mathbb{P}^{\otimes n}$ we can create projector $\hat{P}_{aA} = \frac{I+(-1)^{a}A}{2}$ which maps any state to the $(-1)^a$ eigenspace of the pauli operators $A$.
#### Properties : 
1. $aA \:\hat{P}_{aA} = \hat{P}_{aA}$ and $\hat{P}_{aA} \:aA = \hat{P}_{aA}$
2. For $B \in \mathbb{P}^{\otimes n}$, $\hat{P}_{aA} \: B  \: = \: B \: \hat{P}_{(a \oplus A \odot B)A}$ where $\oplus$ is addition modulo 2 and $\odot$ indicates the commutation of the two pauli operators (cf [Main Note](Main Note)).

### Pauli Exponential Sequence
For any pauli $A \in \mathbb{P}$ we can construct a pauli-exponential $A(\theta)  \: = \: e^{-i \theta A}$. Given any ordered sequence of paulis $\mathcal{E}= (A_{1}, A_{2}, A_{3}, \dots A_{t})$ we can construct an unitary paramterized by the anlge of rotation for each individual pauli as $$\mathcal{E}(\theta)  \: = \: A_{1}(\theta_1) A_{1}(\theta_2) \dots A_{1}(\theta_t) $$
Any arbitrary unitary can be expressed as a parameterized exponential sequence, the most trivial example being the case of arbitrary single qubit unitary expressed as a sequence of $X-Z-X$ roation parameterized by relevant angles. 

#### Properties 
1. The order is not strict, as if there are two commuting paulis then their corresponding pauli-exponentiations will also commutes. To account for this we instead define a partial order $\prec$ over the paulis, which  $(\mathcal{E},\prec) = (A_1 \prec A_2, A_{3}\prec \dots \prec A_{t-2}, A_{t-1}, A_t)$ captures the fact the elements that are not comparable under the $\prec$ must be commuting. 
2. For any pauli $B$, $A(\theta) \:B = B A( (-1)^{A \odot B}\theta)$
3. **Product Rotation Lemma :**  For any projector $\hat{P}_{bB}$ and pauli-exponentials $A(\theta)$ the following holds $$A(\theta) \: \hat{P}_{bB} = AB(b \theta) \:\hat{P}_{bB}$$
---
## Pauli Exponential Extraction 
(cf. [RMWsim21]) Following our discussion we can realise that any measurement pattern in the conventional sense can be written as 
$$ \prod_{i \in (\mathcal{M}, \prec)} \left(\hat{P}_{m_iM_{i}}E_i(\theta_{i})\right) \: \ket{\mathcal{S}_{G},\psi_{in}}$$
 where
- $\mathcal{S}_{G}$ corresponds to the stabilizers of the graph-state and $\psi_{in}$ is the arbitrary input state.  
- $\hat{P}_{m_iM_{i}}$ corresponds the measurement on the $i$ th qubit, $m_i$ denotes the measurement outcome
- $E_i(\theta_{i})$ correponds to the rotation prior to the measurement,( in [RMWsim21] this corresponds to eq 5). 
- Note that here $M_i \odot E_i =1$ as otherwise we can move the pauli-exponential through the projector

The main aim is to extract all the exponentials sandwiched between the projectors, so that we can find an equivalent unitary operation on the system. The existence of (focussed)gflow guarantees that this should always be possible, independent of the choice of the paramaterization angles $\theta$. 

**NB:** We will assume that we are using a focussed-gflow in our discussions, any gflow $(C, \prec)$  if exists in an open-graph can always be focussed to construct a focussed-gflow $(C_{f}, \prec)$ , and as i mentioned focusing a gflow only changes the correction-set and not the partial order. 

If gflow exists we can always find a $\forall_i \: C_{i}\in \braket{\mathcal{S}_G}$ such that 
- $C_{i} \odot E_{i}=0$
- $C_{i} \odot M_{i}=1$
- $C_{i}E_{i}$ has no support on the measured qubit $i$

Summarising the above conditions $C_i$ in most general circumstances can be factorised as 
$$C_{i}  \: = \: \left( \right)_{\mathcal{O}}  \otimes \left( \right)_{\mathcal{O}^{c}\setminus i} \otimes \left( \right)_{i}  $$, the main takeaway from the structure is the fact that upon the action of the measurement via $\hat{P}_{mM}$  only the part acting on the output qubits remain and thus allows us to construct the unitary that was implemented by the measurement pattern.