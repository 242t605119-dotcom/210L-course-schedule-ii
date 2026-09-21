# LeetCode 210 - Course Schedule II

## Problem Description

There are `numCourses` courses numbered from `0` to `numCourses - 1`.

Some courses have prerequisites. A prerequisite means that one course must be completed before another course can be taken.

The task is to return an ordering of courses that allows all courses to be completed.

If it is impossible because of a cycle in the prerequisites, return an empty array.

## Example

Input:

numCourses = 2
prerequisites = [[1,0]]

Course `0` must be completed before course `1`.

A valid order is:

[0,1]

Output:

[0,1]

## Approach

We use **Topological Sorting** with **BFS**.

First, we create a graph to store which courses depend on each course.

The `indegree` array stores the number of prerequisites for each course.

Courses with an indegree of `0` can be taken immediately, so we add them to a queue.

Whenever we complete a course, we decrease the indegree of the courses that depend on it. If their indegree becomes `0`, they are added to the queue.

If all courses are added to the result, the ordering is possible. Otherwise, there is a cycle and we return an empty list.

## Algorithm

1. Create an adjacency list for the courses.
2. Calculate the indegree of every course.
3. Add all courses with indegree `0` to the queue.
4. Remove a course from the queue and add it to the result.
5. Decrease the indegree of its dependent courses.
6. Add courses whose indegree becomes `0` to the queue.
7. Continue until the queue becomes empty.
8. If all courses are included, return the order.
9. Otherwise, return an empty list.

## Time Complexity

**O(V + E)**

Where `V` is the number of courses and `E` is the number of prerequisite relationships.

## Space Complexity

**O(V + E)**

The graph, indegree array, queue, and result list require extra space.

## Key Concepts

- Graph
- BFS
- Topological Sort
- Queue
- Indegree
- Cycle Detection

## Author

T.nandhini
