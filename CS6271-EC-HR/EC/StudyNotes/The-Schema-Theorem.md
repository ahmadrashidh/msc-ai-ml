> How [[Schemata]] will change over time? or survival of [Schemata]

Three parts of any GA:
- Reproduction - selection of schema
- Crossover - break up schema that may affect fitness
- Mutation - changes specified position that may affect fitness

Genotype is referred in upper case letter, a gene in lower case letter
Ex: A = a1a2a3a4a5

Having m examples of individual at moment t

m(A, t) refers to current number of individuals in the population

### Selection

$f(i)$/$\hat{f}$
where $\hat{f}$ - average fitness of the population
$f(i)$ - fitness of the individual

### Reproduction

Reproductive Schema Growth Equation:
m(A ,t+1)  >= m(A , t).$f(A)$/$\hat{f}$
where m(A , t) - current no. of individuals in the population
$f(A)$/$\hat{f}$ - probability of being chosen
That is, more fit schemata increases, less fit decreases


### Crossover

A schema survives if crossover site occurs outside of defining length:
$\delta(A)/(l-1)$
where l is the length of the individual
$\delta(A)$ - defining length

p<sub>s</sub> >= 1 - p<sub>c</sub>.\[$\delta(A)/(l-1)$]
where p<sub>s</sub> - prob of survival
p<sub>c</sub> - prob. of crossover
$\delta(H)/(l-1)$ - prob. that crossover destroy the schema

Therefore, above equation becomes:

m(A ,t+1) >= m(A , t).\[$f(A)$/$\hat{f}$]\[1 - p<sub>c</sub>.$\delta(A)/(l-1)$]

### Mutation

- Each fixed position in A must survive
	=> 1 - p<sub>m</sub>
	=> (1 - p<sub>m</sub>)<sup>o(A)</sup>
	where p<sub>m</sub> -> prob. of mutation
	O(A) -> Order of the schema
For small values i.e. p<sub>m</sub> << 1, the eq. approximates to
1 - o(A).p<sub>m</sub>

Now, the equation becomes:
m(A ,t+1)  >= m(A , t).\[$f(A)$/$\hat{f}$]\[1 - p<sub>c</sub>.$\delta(A)/(l-1)-o(A)$.p<sub>m</sub>]
where m(A , t) - current no. of individuals in the population
$f(A)$/$\hat{f}$ -> probability of being chosen
p<sub>c</sub> -> prob. of crossover
$\delta(H)/(l-1)$ -> prob. that crossover destroy the schema
1 - o(A).p<sub>m</sub> -> prob. that mutation destroying the schema

### Summary on Schema Theorem

- Schema Theorem helps design operators
	- Crossover operators
	- Selection Operators
		- Greedy/Extinctive i.e. based on fitness
		- Not-fitness based
- Why care about schemata?

### Wild Claims

- The original Schema Theorem claims increase in best fit schemata. The theorem will always converge on an optimal solution.
- But remember, No Free Lunch Theorem
- Deceptive problems












