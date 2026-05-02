# Final Project: Formal Verification of a Greedy Algorithm

**Author:** Chris Valdez

## Project Overview
This project provides a formal verification of a greedy selection algorithm using Rocq. The main objective is to prove that for a list of natural numbers, a simple greedy filter is both correct and optimal.

## Files Included
* **`FinalProject.v`**: This file contains the implementation of the greedy algorithm, the definition of the subset (sublist in this case) relation, and all relevant proofs for correctness, completeness, and optimality.

## Important Definitions

### 1. `subset`
An inductive relation that defines what it means for a list to be a subset of another. It enforces that elements are selected without changing their original order, which is important for proving that the greedy algorithm is a valid selection method.

### 2. `greedy_list`
The main algorithm of the project which proccesses a list recursively. If an element is less than or equal to "n" then it is added, otherwise it is skipped.

### 3. `less_forall` 
Checks if all elements in the list satisfy the threshold "n"

### 4. `less_count`
Determines the total number of valid elements available in the original list.

### Logic Helpers
### 1. 'eq_less_than`
Compute boolean checks and mathematical proofs about numbers being smaller or larger than each other.

### 2. `eq_sec_greater` 
Compute boolean checks and mathematical proofs about numbers being smaller or larger than each other.


## Key Lemmas and Theorems

### Correctness
* **`greedy_check_less`**: Proves that every element in the output of the greedy algorithm is less than "n"
* **`greedy_complete`**: Proves that the algorithm's output is a subset of the input list.

### Optimality
* **`subset_eq_all`**: Lemma proving that any arbitrary subset cannot exceed the length of the total count of valid elements in the parent list.
* **`greedy__opt`**: The main theorem of the project. It formally proves that for any subset that satisfies the threshold condition, its length is less than or equal to the length of the list produced by the greedy algorithm.

### Properties
* **`greedy_add`**: A mproof showing that increasing the threshold "n" produces a result that is a subset of the result produced by a higher threshold.

## Unfinished Work
I originally proposed a formal verification of the **A* Search Algorithm** using the **Iris** framework. However, due to the significant complexity of formalizing graph heuristics and managing separation logic within the project's timeframe, I pivoted to the verification of this greedy list algorithm. This allowed for a complete and rigorous proof of optimality while still exploring the themes of greedy strategies and formal correctness.
