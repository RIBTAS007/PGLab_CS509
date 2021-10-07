# PG LAB (CS509)

## Assignment 1

For this assignment, you are expected to implement Dijkstra's algorithm on directed graphs. The dataset is provided.
Note this dataset would likely be a large graph (around 100,000 nodes).
Description of Input:
The input would consist of the following two files. Your code may assume that these files are present in the same
directory as your code.
Nodes.txt -- This file contains information about the nodes of the graph. Data in the file is according to the following
scheme
<Node id as an positive integer> <new line>
<Node id as an positive integer> <new line>
....
Following can be considered as a sample Nodes.txt
343234
8223
123121
....
Edges.txt --- This file contains information about the edges of the graph. Data in the file is according to the following
scheme
<head Node id> <tail Node id> <edge weight as a positive integer> <new line>
<head Node id> <tail Node id> <edge weight as a positive integer> <new line>
....
Following can be considered as a sample Edges.txt
343234 8223 23
123121 8223 89
