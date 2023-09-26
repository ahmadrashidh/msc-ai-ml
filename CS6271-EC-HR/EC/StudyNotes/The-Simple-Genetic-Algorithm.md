Refer Slides for History

Representation - Fixed Length Binary String
Fitness - Depends on the problem
Selection - Based on fitness which one would choose
Crossover Probability
Mutation Probability

## Sample Problems

### One Max
> Evolve strings with many 1s as possible

Representation - Binary
Fitness - Total number of ones in the string
Fitness method - Sum the bit

### Function Optimisation
> Find the global maximum of Shekel's function

Representation - Real Values
Fitness - Return value of function
Fitness method - Individual is made up of two parts; insert them into 
	f(x) = $\sum_{i=1}^{m}$ (c<sub>i</sub> + $\sum_{j=1}^{n}$(x<sub>j</sub> - a<sub>ji</sub>)<sup>2</sup>)<sup>-1</sup>
Note! This could be an n dimensional problem!

### Optimising Flash Memory
> Choose a set of parameters that will make a piece of flash memory withstand 5,000 program/erase cycles

Representation - Binary
Fitness - Number of errors after 5000 p/e cycles
Method - 
- Individuals have one dimension for each parameter = 1200 8-bit parameters]
- Instantiate parameters on flash 
- Cycle 5K times; count errors.

## One Max Problem

Representation - Binary
Fitness - Total number of ones in the string
Fitness method - Sum the bit
Population Size - 5
Crossover Probability - 0.7
Mutation Probability - 0.01
Selection - Roulette Wheel Selection

Sample Individual:
1101101100 
Fitness - 6

### Roulette Wheel Selection
> The larger the fitness of an individual is, the more likely is its selection. Therefore, that individual fitness is proportional to its likelihood of selection.

### Lurking Beneath

- The Schema Theorem - that genetic algorithm will always find a solution
	vs The No Free Lunch Theorem - that cost of space of all problems run on all algorithms, their average performance is same

- Convergence vs Diversity
- Exploration vs Exploitation - At some point, we have stop exploring genetic material to find best fitness and start exploiting to find solution
- How to deal with stochastic algorithms

