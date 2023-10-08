Used to evolve expressions or programs

## Symbolic Regression
> a regression analysis in which the goal is to discover a mathematical expression or formula using symbolic function to map input variables to output variables.


- Task is to identify function f(x1,x2,..xN) that generates y
- x can be any numeric data
- Building Blocks
	- Arithmetic function
	- Input variables
- No prior knowledge about how complex that function could be

## Syntax Trees (or Expression Trees)
> Genetic Programming is tree-based representation

Leaves
- Terminals
- Variables & Constants
Internal Nodes
- Functions
- Operators


### Initialisation

- Full
	- User-specified `Max Depth`. All Individuals are exactly that size
	- Algorithm - if node is less than `Max Depth`, insert function
- Grow
	- User-specified `Max Depth`. All Individuals are exactly that size
	- Algorithm - if node is less than `Max Depth`, randomly function or terminal, otherwise insert terminal
- Ramped Half-and-Half
	- Half created with `full`; the other half with `grow`
	- Individuals within range of depth limits up to `Max Depth`

## Fitness

- Problem Dependent
- Each individual in training case is evaluated
- For symbolic regression, evaluation is `Mean-Squared Error`

### Mean-Squared Error

1/n\[$\sum$ 1 -> n ($Y$<sub>i</sub> - $\hat{Y}$<sub>i</sub> )]<sup>2</sup>

that is,
1. Evaluate individual on each training case
2. Square the difference
3. Calculate the mean


## Selection Algorithms
> Same as EA/GA

## Crossover
> Crossover is done on subtree level

In GP, it is guaranteed that offspring is syntactically valid, but semantically may be invalid

## Constraints

Closure
- All functions use and return same type
Evaluation Safety
- Syntax vs Semantics
	Can be semantically invalid expression/program, for example, Zero Division Problem

	__*Protected Operators*__ verify that argument make sense e.g. Protected Division using modulo


## Mutation

1. Point Mutation
	Select a node and change it. Functions can only be changes with functions.
2. Subtree mutation

## GP Steps

1. Identify Function Set
2. Identify Terminals
	- Data labels
	- Maybe some constants
	- Maybe an Ephemeral Random Constant (ERC) -> a constant  designed to have different constant value for each individual - more flexibility and diversity in search of an optimal solution

## GP Parameters

1. Population: 300 - 500
2. Generations: 50
3. Min/Max Depth: 3 - 17
4. Initialisation Type: Ramped Half and Half
5. Crossover: 0.7
6. Mutation: 0.01


## Even Parity Problem

