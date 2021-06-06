# Rubiks Cube Solver

The file *Source.cpp* contains the implementation of Rubik's Cube Solver using:
  1. Iterative Deepening Search
  2. A* Search using Heuristics
  
In Iterative Deepening, we use both DFS and BFS techniques to traverse a tree depth by depth. Initially, depth is initialized to zero and then we compare all possible nodes at given depth and traverse them using a combination of DFS and BFS using recursion until the goal is found or the depth level exceeds the provided limit. It is an exhaustive approach in terms of time and space complexity.
Face Descriptions:
  •	Front face=0
  •	Top face=1
  •	Back face=2
  •	Bottom face=3
  •	Right face=4
  •	Left face=5
  
The file *file.txt* contains the face structure of cube for start and final phases respectively.

Each face has two rotations, clockwise and anticlockwise.
In A* algorithm, we use a heuristic function to guide the search of the nodes until the goal is found or the queue holding nodes becomes empty. The heuristic function takes the current state of the cube and compares all faces index by index excluding the same color indexes with the goal state of cube. Manhattan distance is calculated for each face, summed up and divided by 12 as each rotation moves 12 indexes. 

# Results

Depth	  Nodes-Traversed	    Time (in seconds)
	      IDS	    A*	          IDS	  A*
1	      11	    2	            1	    1
2	      103	    5	            1	    1
3	      889	    7	            1	    <1
4	      4660	  9	            1	    <1
5	      95145	  25	          20	  3
6	      909505	40	          197	  10

As it is evident from the Results mentioned above, A* performs exceptionally well at depths of larger magnitude than IDS. A* traverses minimum nodes and takes much less time than IDS.
