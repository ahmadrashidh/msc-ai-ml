
## Fitness Landscapes

- Describes how difficult the problem is
- The landscape where we find optimum point

### Exploration vs Exploitation

- Crossover can takes large steps - explores the space
- Mutation can take smaller steps - exploits what we already have

## Continuous Optimisation

### Blended Crossover (BX)

- Creates offspring similar to the parents, not identical
- For each dimension:
	- Select value from an interval twice as wife as the interval between the parents
		=> \[parent1 - $\alpha$(parent2 - parent1),parent1 + $\alpha$(parent2 - parent1)]
		where $\alpha$ is usually set to 0.5

### Simulated Blended Crossover (SBX)

- Creates offspring who's average is equal to their parents
- \[parent1 - $\beta$(parent2 - parent1),parent1 + $\beta$(parent2 - parent1)]
	where $\beta$ is the spread factor - calculated from crowding factor ($\mu$)
	High $\mu$, more similar to parents - ranges from 10 to 20
- Calculating $\beta$:
	1. Calculate u - random number from 0 to 1
	2. If u <= 0.5, $\beta$ = (2u)<sup>1/mu+1</sup>
	3. Otherwise, $\beta$ = (1/2(1-u))<sup>1/mu+1</sup>

### Mutation

- Gaussian - modifies based on Gaussian Distribution
- Polynomial Bounded - modifies within bounded range

## Multi-objective Fitness

Many real word problems are multi-objective, for example, 
1. program that is both correct and short
2. knapsack that is high valued and below the weight limit

__Dominated Solution__
Another Solution that is better at all objectives
__Non-dominated solution__
No dominating solution exists
__Pareto Optimal__
One objective can't get any better without the others getting worse

### NSGA II
> Non-dominated Sorting Genetic Algorithm

- Identify individuals on the first front - Pareto front (on RMSE vs Size graph)
- Calculate their non-domination rank - rank acc. to others in the front
- Calculate their crowding distance - higher value means fewer nearby solutions -> if we draw cuboid using neighbours, crowding distance is the size of the perimeter

### GP and NSGA II

Objective 1: Minimise error
Objective 2: Minimise tree size
