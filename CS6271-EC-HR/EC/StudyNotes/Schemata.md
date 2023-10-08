String => Chromosome/Genotype
Each character in the string => Gene/Feature/Character
Allele => Feature value
- Value of each character
- For SGA, Allele is either 0 or 1
Phenotype = Decoded Genotype
- Problem Dependent
- Refers to parameter, character, program
- Can be said physical expression of gene in DNA

### Schema
> Is a similarity template

\* is nothing but wildcard

Defining length ($\delta$(H)) - difference between first and last character
where H is Schema

Order - Number of Specified positions

1**** => $\delta$(H) = 0, O = 1
0**** => $\delta$(H) = 0, O = 1
11*** => $\delta$(H) = 1, O = 2
1***\1 => $\delta$(H) = 4, O = 2


### Search Space

- Each individual length l has 2<sup>l</sup> schemata, therefore population of n contains n.2<sup>l</sup>

### Schemata or Individuals

- What do we want? Highly fit individuals
- How do we find? 
	- How does GA build good individuals?
		- By promoting good schema
		- By not breaking them
