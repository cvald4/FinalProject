# Final Project: Formal Verification of a Greedy Algorithm

**Author:** Chris Valdez
**Date:** May 1, 2026

## Project Overview
This project provides a formal verification of a greedy selection algorithm using the **Coq Proof Assistant**. The core objective is to prove that for a list of natural numbers, a simple greedy filter is both correct (it only picks valid elements) and optimal (it picks the maximum possible number of valid elements).

## Files Included
* **`GreedyProof.v`**: This file contains the implementation of the greedy algorithm, the definition of the sublist relation, and all supporting proofs for correctness, completeness, and optimality.

## Core Definitions

### 1. `subset`
An inductive relation that defines what it means for one list to be a sublist of another. It ensures that elements are selected without changing their original order, which is critical for proving that the greedy algorithm is a valid selection process.

### 2. `greedy_list`
The primary algorithm. It processes a list recursively: if an element is less than or equal to a threshold $n$, it is included; otherwise, it is skipped.

### 3. `less_forall` & `less_count`
Supporting recursive properties. `less_forall` checks if all elements in a list satisfy the threshold, while `less_count` determines the total number of valid elements available in the original list.

## Key Lemmas and Theorems

### Correctness
* **`greedy_check_less`**: Proves that every element in the output of the greedy algorithm is $\leq n$.
* **`greedy_complete`**: Proves that the algorithm's output is a legitimate `subset` of the input list.

### Optimality
* **`subset_eq_all`**: A fundamental lemma proving that any arbitrary valid subset cannot exceed the length of the total count of valid elements in the parent list.
* **`greedy__opt`**: The main theorem of the project. It formally proves that for any subset $s$ that satisfies the threshold condition, its length is less than or equal to the length of the list produced by the greedy algorithm. This confirms that the greedy approach is optimal.

### Properties
* **`greedy_add`**: A monotonicity proof showing that increasing the threshold $n$ produces a result that is a subset of the result produced by a higher threshold.

## Unfinished Work
I originally proposed a formal verification of the **A* Search Algorithm** using the **Iris** framework. However, due to the significant complexity of formalizing graph heuristics and managing separation logic within the project's timeframe, I pivoted to the verification of this greedy list algorithm. This allowed for a complete and rigorous proof of optimality while still exploring the themes of greedy strategies and formal correctness.
