# DSA Patterns & Problem-Solving Framework

## A Comprehensive Guide to Mastering Technical Interviews

---

## 📖 Table of Contents
1. [The DSA Pattern Recognition Toolkit](#-the-dsa-pattern-recognition-toolkit)
2. [The 5-Step Pattern Decision Framework](#-the-5-step-pattern-decision-framework)
3. [How to Differentiate Similar Patterns](#-how-to-differentiate-between-similar-patterns)
4. [Applying the Framework to Real Problems](#-applying-the-framework-solve-20-valid-parentheses)
5. [Solved Examples with Pattern Analysis](#-solved-examples-with-pattern-analysis)
   - [Example 1: 20. Valid Parentheses](#example-1-20-valid-parentheses)
   - [Example 2: 834. Sum of Distances in Tree](#example-2-834-sum-of-distances-in-tree)
   - [Example 3: 792. Number of Matching Subsequences](#example-3-792-number-of-matching-subsequences)
6. [Quick Reference Cheat Sheet](#-quick-reference-cheat-sheet)

---

## 🧩 The DSA Pattern Recognition Toolkit

Here is a summary of the most essential DSA patterns, their key indicators, and example problems to help you build your mental library.

| Pattern | Core Idea & Typical Complexity | Key Indicators / Trigger Questions | Classic LeetCode Problems |
| :--- | :--- | :--- | :--- |
| **Sliding Window** | Maintains a dynamic, contiguous 'window' over an array or string to avoid re-computation. **O(n)**. | "...contiguous subarray/substring...", "...maximum/minimum sum of size K...", "...longest substring with at most K distinct characters..." | [3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/), [209. Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/) |
| **Two Pointers** | Uses two indices to traverse a data structure, often from opposite ends or same direction. **O(n)**. | "Sorted array", "...pair/triplet sum...", "...palindrome check...", "...merge two sorted arrays..." | [11. Container With Most Water](https://leetcode.com/problems/container-with-most-water/), [15. 3Sum](https://leetcode.com/problems/3sum/) |
| **Fast & Slow Pointers** | Two pointers moving at different speeds (e.g., slow +1, fast +2). Essential for cycle detection in linked lists. **O(n)**. | "...linked list cycle...", "...find the middle of a linked list...", "...find the duplicate number in an array...", "Floyd's Cycle Detection" | [141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/), [287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/) |
| **Binary Search** | Repeatedly divides the search interval in half. Works on sorted data or a monotonic search space. **O(log n)**. | "Sorted array", "...logarithmic time...", "...find the minimum in a rotated sorted array...", "...search in a 2D matrix..." | [33. Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/), [4. Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/) |
| **BFS / DFS** | Core graph traversal techniques. BFS uses a queue and finds shortest paths in unweighted graphs; DFS uses a stack or recursion to explore deep paths. **O(V+E)**. | "...shortest path in a graph/maze...", "...connected components...", "...tree level order traversal...", "...number of islands..." | [200. Number of Islands](https://leetcode.com/problems/number-of-islands/), [102. Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/) |
| **Dynamic Programming (DP)** | Solves complex problems by breaking them into overlapping subproblems and storing their solutions (memoization/tabulation). **O(n²) or better**. | "...maximum/minimum path sum...", "...number of ways to reach a point...", "...longest increasing subsequence...", "...optimal value..." | [53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/), [300. Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/) |
| **Greedy** | Makes the locally optimal choice at each stage with the hope of finding the global optimum. Not always optimal, but very efficient when it works. **O(n log n) or O(n)**. | "...interval scheduling...", "...maximum profit from stock...", "...minimum number of coins..." (in canonical currencies), "...jump game..." | [55. Jump Game](https://leetcode.com/problems/jump-game/), [435. Non-overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/) |
| **Backtracking** | A systematic way to iterate through all possible configurations of a search space. It's an optimized DFS that "prunes" paths that can't lead to a solution. **O(2ⁿ) or O(n!)**. | "...generate all combinations/permutations...", "...N-Queens...", "...sudoku solver...", "...word search..." | [46. Permutations](https://leetcode.com/problems/permutations/), [51. N-Queens](https://leetcode.com/problems/n-queens/) |
| **Heap (Priority Queue)** | Efficiently maintains the min or max element in a dynamic set. **O(n log k)**. | "...top K largest/frequent elements...", "...merge K sorted lists...", "...kth smallest element in a stream..." | [215. Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/), [23. Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/) |
| **Prefix Sum** | Precomputes cumulative sums to answer range sum queries in O(1) time. **O(n) preprocess, O(1) per query**. | "...sum of a subarray...", "...equilibrium index...", "...range sum query..." | [560. Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/), [303. Range Sum Query - Immutable](https://leetcode.com/problems/range-sum-query-immutable/) |
| **Union-Find** | Manages a partition of a set into disjoint subsets, useful for dynamic connectivity. **Nearly O(1) per operation**. | "...connected components...", "...detect cycle in an undirected graph...", "...number of provinces...", "friend circles" | [323. Number of Connected Components in an Undirected Graph](https://leetcode.com/problems/number-of-connected-components-in-an-undirected-graph/), [547. Number of Provinces](https://leetcode.com/problems/number-of-provinces/) |
| **Topological Sort** | Orders vertices in a directed acyclic graph (DAG) such that for every directed edge `u→v`, `u` comes before `v`. **O(V+E)**. | "...task scheduling...", "...course prerequisite...", "...build order...", "...dependency graph..." | [207. Course Schedule](https://leetcode.com/problems/course-schedule/), [210. Course Schedule II](https://leetcode.com/problems/course-schedule-ii/) |
| **Trie (Prefix Tree)** | A tree-like data structure for storing strings, allowing for fast prefix-based operations. **O(L) per operation**. | "...autocomplete...", "...spell checker...", "...word search with prefix...", "...longest common prefix..." | [208. Implement Trie (Prefix Tree)](https://leetcode.com/problems/implement-trie-prefix-tree/), [212. Word Search II](https://leetcode.com/problems/word-search-ii/) |
| **Monotonic Stack** | Maintains a stack of elements in increasing or decreasing order to solve "next greater/smaller element" type problems efficiently. **O(n)**. | "...next greater element...", "...daily temperatures...", "...largest rectangle in histogram..." | [739. Daily Temperatures](https://leetcode.com/problems/daily-temperatures/), [84. Largest Rectangle in Histogram](https://leetcode.com/problems/largest-rectangle-in-histogram/) |

---

## 🤔 The 5-Step Pattern Decision Framework

Here's a structured thought process you can use to tackle any problem.

### Step 1: Restate & Analyze

Carefully rephrase the problem in your own words:
- What is the input? (array, string, tree, graph)
- Is it sorted or unsorted?
- What is the desired output? (value, subset, path, count, boolean)
- This initial classification is the first filter.

### Step 2: Check the Constraints

This is the most critical step in choosing the optimal pattern:
- `n <= 10-15` → Brute force or Backtracking might be acceptable.
- `n <= 20` → Backtracking with a state vector (e.g., Bitmasking) might be viable.
- `n <= 500-1000` → O(n²) dynamic programming (DP) could be the solution.
- `n <= 10⁵` → You need an O(n log n) or O(n) solution.
- `n <= 10⁶` → Aim for O(n) or O(1) space solutions.

### Step 3: Scan for Keywords

Look for specific terms that act as clues:
- **Keywords like "sorted" or "pair"** → Think Two Pointers or Binary Search.
- **Keywords like "subarray" or "window"** → Points to Sliding Window.
- **Keywords like "generate" or "all combinations"** → Points to Backtracking.
- **Keywords like "shortest path" or "minimum steps"** → Often indicates Breadth-First Search (BFS).

### Step 4: Try a Small Example

Don't just think abstractly:
- Take a simple, small input and try to solve it manually.
- This often reveals the fundamental pattern of the problem.
- As you solve, ask yourself: "What information did I keep track of to get the answer?"

### Step 5: Map to Known Problems

Once you have a candidate pattern, ask:
- "Is this problem a variation of a classic problem I've seen?"
- Example: "find if two numbers sum to a target" → Two Sum problem → hash map (O(n)) or, if the array is sorted, two pointers (O(n log n)).

---

## 💡 How to Differentiate Between Similar Patterns

### Sliding Window vs. Two Pointers

| Aspect | Sliding Window | Two Pointers |
|--------|----------------|---------------|
| **Maintains** | Contiguous range (window) | Two positions (not necessarily contiguous) |
| **Movement** | Usually left and right expand/shrink sequentially | Can move from ends or both same direction |
| **Typical use** | Subarray/substring conditions | Pair sum, palindrome, merging |
| **Example** | Longest substring without repeating chars | Container with most water |

### BFS vs. DFS vs. Backtracking

| Aspect | BFS | DFS | Backtracking |
|--------|-----|-----|---------------|
| **Goal** | Shortest path, level order | Explore all, connectivity | Generate all valid combinations/permutations |
| **Data structure** | Queue | Stack (implicit recursion) | Recursion + pruning |
| **State revisited** | Yes (visited set) | Yes (visited set) | Yes (choices made, undo) |
| **Typical** | Word ladder | Number of islands | N-Queens, subsets |

### DP vs. Greedy

| Aspect | DP | Greedy |
|--------|----|--------|
| **Choice** | Considers all possibilities, uses past results | Makes myopic optimal choice |
| **Optimal substructure** | Required | Required |
| **Overlapping subproblems** | Yes | Not necessary |
| **Can fail if** | No, always optimal if correctly defined | Yes, if local optimum ≠ global |
| **Classic** | Knapsack, LCS | Activity selection, Dijkstra (with non-negative edges) |

---

## 💻 Applying the Framework: Solve "20. Valid Parentheses"

Let's use our framework to solve the classic problem **"20. Valid Parentheses"**.

### Step 1: Restate & Analyze
- We're given a string containing only the characters `'('`, `')'`, `'{'`, `'}'`, `'['`, and `']'`.
- We need to determine if the input string has a valid parentheses structure.
- This is a simple **string** problem.

### Step 2: Check the Constraints
- The string length can be up to `10⁴` (10,000).
- An O(n²) solution is too slow, but an O(n) or O(n log n) solution is ideal.

### Step 3: Scan for Keywords
- "parentheses" and "valid" → classic way to handle parentheses matching is to use a **Stack**.
- Push opening parentheses onto the stack, and when you see a closing one, pop the stack to check if it's the correct matching type.

### Step 4: Try a Small Example

Input: "{[()]}"
1. `{` -> push
2. `[` -> push
3. `(` -> push
4. `)` -> pop `(` matches `)` -> valid
5. `]` -> pop `[` matches `]` -> valid
6. `}` -> pop `{` matches `}` -> valid

After processing, the stack is empty → string is valid.

### Step 5: Map to Known Problems
This is a classic use of a stack. The algorithm:
- Iterate through each character `c` in the string.
- If `c` is an opening bracket, push it onto the stack.
- If `c` is a closing bracket, check the top of the stack. If empty or doesn't match, return `false`.
- After processing all characters, return `true` if stack is empty.

### Java Implementation

```java
import java.util.ArrayDeque;
import java.util.Deque;
import java.util.HashMap;
import java.util.Map;

class Solution {
    public boolean isValid(String s) {
        Deque<Character> stack = new ArrayDeque<>();
        Map<Character, Character> matchingBrackets = new HashMap<>();
        matchingBrackets.put(')', '(');
        matchingBrackets.put('}', '{');
        matchingBrackets.put(']', '[');

        for (char c : s.toCharArray()) {
            if (matchingBrackets.containsKey(c)) {
                if (stack.isEmpty() || stack.pop() != matchingBrackets.get(c)) {
                    return false;
                }
            } else {
                stack.push(c);
            }
        }
        return stack.isEmpty();
    }
}

Time Complexity Decision Tree
n ≤ 10-15     → Brute force / Backtracking (2^n, n!)
n ≤ 20        → Bitmask DP (2^n)
n ≤ 1000      → O(n²) DP
n ≤ 10⁵       → O(n) or O(n log n)
n ≤ 10⁶       → O(n) only


Pattern Selection Flow
Input Type:
├── Array/String
│   ├── Sorted → Binary Search or Two Pointers
│   ├── Contiguous subarray → Sliding Window
│   ├── Pairs/Triplets → Two Pointers (if sorted) or HashMap
│   ├── All combinations → Backtracking
│   └── Optimal value → DP or Greedy
├── Tree/Graph
│   ├── Shortest path → BFS (unweighted) or Dijkstra (weighted)
│   ├── Connectivity → DFS or Union-Find
│   ├── Level order → BFS
│   ├── Dependencies → Topological Sort
│   └── All nodes calculation → Rerooting DP
├── Linked List
│   ├── Cycle detection → Fast & Slow Pointers
│   ├── Merge sorted lists → Two Pointers
│   └── Reverse / Reorder → Recursion or Iterative
└── String
    ├── Substring condition → Sliding Window
    ├── Parentheses → Stack
    ├── Prefix operations → Trie
    └── Multiple pattern matching → Bucket Queue or Suffix Array
