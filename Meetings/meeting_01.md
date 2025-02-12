# Meeting 01

_Meeting will take place on 24th June 2021, at 13:30 IST._


## Tasks for this sprint
- [x] Go through the tooling and pick one,
    - [x] Minizinc Python API
        - [x] Read Documentation.
        - [x] Implement a model.
    - [x] CPMpy
        - [x] Read Documentation.
        - [x] Implement a model.
- [x] Read up on Copeland method and (weighted) tournament solutions.
- [x] Briefly go through the current codebase.

### SAT 19th June 2021
- Read up on Copeland Method
- Watched CP talk
- Read through CPpy paper
- Went through the minizinc tutorial on the [Minizinc website](https://www.minizinc.org/doc-2.5.5/en/part_2_tutorial.html).
### SUN 20th June 2021
- Started work on implementing Copeland Voting in Minizinc
- Went though Minizinc Python API docs
### MON 21th June 2021
- Worked on the Minizinc model.
- The model works, it's a little slow due to the result function which can be optimized but I'm stopping now because it gives the right answer.
### TUE 22th June 2021
- Worked on Copeland Method in Python.
- Went through models from CP course week 1 and 2.
### WED 23th June 2021
- Went through models from CP course week 3.
### THU 24th June 2021
- Started work on the copeland meta search.
- Went through models from CP course week 4.

### FRI 25th June 2021
- Worked on the copeland script
## Copeland Method
- Each agent ranks candidates in order of preference. 
- We now define 2 situations in pairwise comparisons: 
    - Agent A is said to have majority preference over another agent B if more voters prefer A to B than prefer B to A;
    - A preference tie occurs when both A and B have an equal number of votes.
- Copeland Score for a candidate = 
    number of other candidates over whom he or she has a majority preference 
    + half the number of candidates with whom he or she has a preference tie. NOTE: other variations of 1/0.5/0 and 2/1/0 exist.
- The winner of the election under Copeland's Method is the candidate with the highest Copeland score; under Condorcet's method this candidate wins only if he or she has the maximum possible score of n–1 where n is the number of candidates. Hence victory under this system amounts to satisfying the Condorcet criterion.

## CPpy vs. Minizinc API
### CPpy Paper Notes
- Extends ND Arrays like constraints can be defined on them.
- Custom constructs include:
    - BoolVar(shape) and IntVar(lb,ub, shape)
    - minimize() and maximize()
    - implies(left, right) -- construct of Minizinc(->)
    - all() and any() -- overwritten the python methods.
- No mechanism for guiding the solver with predicates, unless extended.
- It's more of a translator at the moment.

### Minizinc Documentation Notes
- Predicates and Functions
    - Global Functions
        - Alldifferent
        - Cumulative
        - Table (Tabular lookup) - tuple of variables takes a value from a set of tuples
        - Regular (DFA)
    - Defining Predicates -- high-level, modular constraint definition
        - Predicates - boolean expressions that can be used to constrain the model.
        - test - useful to be used with predicates, kind of like LTL and neverclaims in model checking.
        - assert, like test.
    - Defining Functions -- similar to Predicates but with more general return types.

## Meeting Questions
- [x] Related papers to the search method we discussed last time.
- [x] Do we have models with a large solution set.
    - [x] Bus Tour not working
## Tasks for next sprint
Go through the already written code.