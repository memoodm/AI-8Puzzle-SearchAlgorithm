# SEARCH ALGORITHM FOR 8 PUZZLE GAME
By: Guillermo Andres De Mendoza Corrales, memoodm@gmail.com, Colombia, Bogota D.C.<br />
Language: Python 3.6<br />
Description: Some search solutions for 8 puzzle game, implementing these algorithms: 
- Breadth-First Search
- Depth-First Search
- A*

## 1. 8 Puzzle game

![8puzzle](https://github.com/memoodm/AI-Search-8Puzzle/blob/master/images/8Puzzle.JPG)

The 8-puzzle (also called Gem Puzzle, Boss Puzzle, Game of Fifteen, Mystic Square and many others) is a 3x3 sliding puzzle that consists of a frame of eight numbered square tiles in random order with one tile missing

## 2. Conceptual background algorrithm

### Breadth-First Search

![BFS](https://github.com/memoodm/AI-Search-8Puzzle/blob/master/images/BFS.gif)

Is an algorithm for traversing or searching tree or graph data structures. It starts at the tree root (or some arbitrary node of a graph, sometimes referred to as a 'search key), and explores all of the neighbor nodes at the present depth prior to moving on to the nodes at the next depth level.

It uses the opposite strategy as depth-first search, which instead explores the highest-depth nodes first before being forced to backtrack and expand shallower nodes.

BFS and its application in finding connected components of graphs were invented in 1945 by Konrad Zuse and Michael Burke, in their (rejected) Ph.D. thesis on the Plankalkül programming language, but this was not published until 1972. It was reinvented in 1959 by Edward F. Moore, who used it to find the shortest path out of a maze, and later developed by C. Y. Lee into a wire routing algorithm (published 1961).

Link: wikipedia -> https://en.wikipedia.org/wiki/Breadth-first_search

### Depth-First Search

![DFS](https://github.com/memoodm/AI-Search-8Puzzle/blob/master/images/DFS.gif)

Is an algorithm for traversing or searching tree or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

A version of depth-first search was investigated in the 19th century by French mathematician Charles Pierre Trémaux as a strategy for solving mazes

Link: wikipedia -> https://en.wikipedia.org/wiki/Depth-first_search

### A*

![Astart](https://github.com/memoodm/AI-Search-8Puzzle/blob/master/images/Astar.gif)

A* (pronounced as "A star") is a computer algorithm that is widely used in pathfinding and graph traversal, which is the process of plotting an efficiently directed path between multiple points, called "nodes". It enjoys widespread use due to its performance and accuracy. However, in practical travel-routing systems, it is generally outperformed by algorithms which can pre-process the graph to attain better performance, although other work has found A* to be superior to other approaches.

Peter Hart, Nils Nilsson and Bertram Raphael of Stanford Research Institute (now SRI International) first published the algorithm in 1968.[3] It is an extension of Edsger Dijkstra's 1959 algorithm. A* achieves better performance by using heuristics to guide its search.

Link: wikipedia -> https://en.wikipedia.org/wiki/A*_search_algorithm
  

## Project input

Execute python via comand prompt:
```sh
python driver.py 'method' 'board state'
```
Where method is the algorithm selected for finding a solution path, and board state is the initial board of the game to start finding a solvable path <br/>

Example bfs:
```sh
python driver.py bfs 8,6,4,2,1,3,5,7,0
```

Example dfs:
```sh
python driver.py dfs 1,2,5,3,4,8,6,7,0
```

Example ast:
```sh
python driver.py ast 1,2,5,3,4,8,6,7,0
```

### Descripcion de start
Inicia el servidor de jboss, el cual incluye el artefacto de apache camel
```sh
start servers\jboss-fuse-6.3.0.redhat-187\bin\fuse.bat
```
Inicia el servidor de glassfish el cual contiene los api's de seleccion de servicios y el testing grafico del aplicativo
```sh
start servers\GlassFish_Server\glassfish\bin\startserv.bat
```
Descarga los docker de servicios utilizados por el proyecto
```sh
docker pull memoodm/services:service_1_rest
docker pull memoodm/services:service_2_soap
docker pull memoodm/services:apiSelector
```
Ejecuta los servicios en docker
```sh
docker run -d -p 8081:8080 memoodm/services:service_1_rest
docker run -d -p 8082:8080 memoodm/services:service_2_soap
docker run -d -p 8888:8080 memoodm/services:Routing
```



