# Description

> In this problem, a rooted tree is a directed graph such that, there is exactly one node (the root) for which all other nodes are descendants of this node, plus every node has exactly one parent, except for the root node which has no parents.
>
> The given input is a directed graph that started as a rooted tree with N nodes (with distinct values 1, 2, ..., N), with one additional directed edge added. The added edge has two different vertices chosen from 1 to N, and was not an edge that already existed.
>
> The resulting graph is given as a 2D-array of edges. Each element of edges is a pair [u, v] that represents a directed edge connecting nodes u and v, where u is a parent of child v.
>
> Return an edge that can be removed so that the resulting graph is a rooted tree of N nodes. If there are multiple answers, return the answer that occurs last in the given 2D-array.

[Redundant Connection II - LeetCode](https://leetcode.com/problems/redundant-connection-ii/)

## Notes

* The given graph is a invalid rooted tree graph with one redundant edge. The tree becomes valid after removing the redundant edge.
* If there are multiple choice to remove, choose the one that is added last.

## Steps

1. Find if any edge will construct a cycle. If an edge will form a cycle, store the edge and ignore it in step 2.
1. Find if any node has two parents.
1. If no node has two parents, the edge found in step 1 is the redundant edge.
1. If a node has two parents, the edge from the second parent to that node is redundant.
1. If a node has two parents and step 1 also found an edge that is forming cycle, the edge from the first parent to that node formed the cycle.

# Test cases

Case 1 | Case 2 | Case 3
-------|--------|-------
![Case 1](assets/case1.png) | ![Case 2](assets/case2.png) | ![Case 3](assets/case3.png)

Case 1 is invalid since node 1 has two parents. After removing the edge from node 1 to node 4, it becomes case 2.

In case 2, both node 3 and 4 have no parent which means there are two root nodes. Also, node 1 still has two parents.

By removing the edge from node 2 to node 1 in case 1, the tree becomes valid and is shown in case 3.

# Solve it by hand



