**Exp no 01 : IMPLEMENT DEPTH FIRST SEARCH TRAVERSAL OF A GRAPH

NAME : VISMAYA.S
REGISTER NUMBER : 212221230125
AIM:
To Implement Depth First Search Traversal of a Graph using Python 3.

THEORY:
Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

#Step 1:
Initially, stack and visited arrays are empty.

![image](https://github.com/VismayaNair/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427210/103d49a1-bdcb-4372-9ba8-7b7b5cc01915)


Queue and visited arrays are empty initially. Stack and visited arrays are empty initially.

#Step 2:
Visit 0 and put its adjacent nodes which are not visited yet into the stack. 
![image](https://github.com/VismayaNair/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427210/4c900e74-d8ef-4a45-b56c-39ec4561d34b)


Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

#Step 3:
Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack. ![image](https://github.com/VismayaNair/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427210/633b2dfb-7d13-48e3-8e75-99d96dd2b108)


Visit node 1 Visit node 1

#Step 4:
Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack. ![image](https://github.com/VismayaNair/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427210/d26108ca-79f3-4703-809f-9819937d04df)


Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

#Step 5:
Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack. image

Visit node 4 Visit node 4

#Step 6:
Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack. ![image](https://github.com/VismayaNair/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427210/72ebb126-955b-4a22-bcdc-b0b2aa5fb82f)


Visit node 3 Visit node 3

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

#ALGORITHM:
Construct a Graph with Nodes and Edges.

Depth First Search Uses Stack and Recursion.

Insert a START node to the STACK.

Find its Successors Or neighbors and Check whether the node is visited or not.

If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.

SAMPLE INPUT:
8 9
A B
A C
B E
C D
B D
C G
D F
G F
F H
SAMPLE OUTPUT:
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']
PROGRAM:
```
from collections import defaultdict
def dfs(graph,start,visited,path):
   path.append(start)
   visited[start]=True
   for neighbour in graph[start]:
       if visited[neighbour]==False:
           dfs(graph,neighbour,visited,path)
           visited[neighbour]=True
   return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
   u,v=map(str,input().split())
   graph[u].append(v)
   graph[v].append(u)
#print(graph)
start=000 2
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)
```
#OUTPUT:

![image](https://github.com/VismayaNair/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427210/3846b43c-5ebd-4826-bb1e-ff05eb94b59c)


#RESULT:
Thus, a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.
