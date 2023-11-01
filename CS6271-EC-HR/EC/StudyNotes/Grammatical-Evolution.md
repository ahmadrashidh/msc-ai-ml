> combination of Genetic Algorithm and Genetic Programming

Inputs to GE system:
1. Grammar - described programs that can be written
2. Fitness function - to test how good programs are
3. Search Engine - nothing but Genetic Algorithms

Output: Solution

### Whats Fitness?

1. Map to program from binary string
2. Compile(may be)
3. Evaluate fitness pretty much same as GP

## Grammars

1. Specify `Legal Sentences` in a language
	x+=3;
2. Tokenise sentence:
	x -> variable token
	+= -> operator token
	3 -> operand token
	; -> terminal

Grammar described by <S,T,N,P>
where S -> start symbol
T -> terminals (operator or operand)
N -> non-terminals
P -> production rules (maps N to T)

__Backaus Naur Form

How Grammatical Evolution works?

