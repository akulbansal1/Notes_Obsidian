
## Programming, Data Structures, and Algorithms using Python
# <u>Week 1</u>

# <u>Week 2</u>

- Resources of interest:
	1. Time — how long the code takes
	2. Space — memory requirement
- Time efficiency:
	- measured as a function of input size $n$
	- $t(n)$
	- Orders of magnitude:
		- when comparing $t(n)$, focus on orders of magnitude and not the constants
	- Typical growth functions:
		- logarithmic: $log_{2}(n)$: binary search (dividing the ordered dataset in two at every step)
		- polynomial: $n^2, n^3, \ldots$: nested loops
		- exponential: $2^n$: number of subsets of $n$
	- Typical basic operations: 
		- compare two values: `y == x`
		- assign a value to a variable: `x = 3`
- Upper bounds: denoted by $O(g(x))$
	- $f(x)$ is said to be $O(g(x))$ if we can find constants $c$ and $x_0$ such that $c \cdot g(x)$ is an upper bound for $f(x)$ for $x$ beyond $x_0$ $$ f(x)\ \leq\ c \cdot g(x) \quad \forall x \geq x_0$$
	- example: $100n + 5$ is $O(n^2)$
		- $100n + 5 \leq 100n + n \quad \forall n \geq 5$  and $100n + n = 101n$
		- $101n \leq 101n^2$
		- $c = 101$ and $n_0 = 5$
		- choice of $n_0$ and $c$ is not unique. $c = 105$ and $n_0 = 1$ is also a solution.
	- **Useful properties**
		- if $f_1(n)$ is $O(g_1(n))$ and $f_2(n)$ is $O(g_2(n))$, then $f_1(n) + f_2(n)$ is $O(max(g_1(n),g_2(n)))$
		- least efficient phase is the upper bound for the whole algorithm.
- Lower bounds : denoted by $\Omega(g(x))$
	- $f(x)$ is said to be $\Omega(g(x))$ if we can find constants $c$ and $x_0$ such that $c \cdot g(x)$ is an lower bound for $f(x)$ for $x$ beyond $x_0$ $$ f(x)\ \geq\ c \cdot g(x) \quad \forall x \geq x_0$$
- Tight bounds: denoted by $\Theta(g(x))$
	- $f(x)$ is said to be $\Theta(g(x))$ if it is both $O(g(x))$ and $\Omega(g(x))$
	- example: $\frac{n(n-1)}{2}$ is $\Theta(n^2)$

- Iterative programs
- Recursive programs

- $\log n$ is the number of time you divide $n$ by $2$ to reach $1$.
	- complexity of Binary Search is $\log n$![[Screenshot 2023-10-06 at 8.18.20 PM.png]]

#### Sorting a list
- ##### Selection Sort
	- scan the entire list and find the minimum element. Repeat with the remaining elements.
	- avoid using a second list by swapping the minimum element into the first position.
	```python
	def SelectionSort(L):
		n = len(L)
		if n < 1:
			return L
	
		for i in range(n):
			position_of_min = i
	
			for j in range(i+1,n):
				if L[j] < L[position_of_min]:
					position_of_min = j
	
			(L[i], L[position_of_min]) = (L[position_of_min], L[i])
		
		return L
	```
	- $T(n) = \frac{n(n+1)}{2}$ is $O(n^2)$
	- order is $n^2$, even in the best case scenario.

- ##### Insertion Sort
	- Move the first element into a new list. Move the second element before/after the first element depending on the value. **Insert** the third element into the correct position w.r.t. to the first two elements.
	```Python
	def InsertionSort(L):
		n = len(L)
		if n < 1:
			return L
		
		for i in range(n):
			# Move L[i] to the correct position in L
			j = i
			
			while j > 0 and L[j] < L[j-1]:
				(L[j], L[j-1]) = (L[j-1], L[j])
				j = j-1
		
		return L
	```
	- complexity is the same as Selection sort
	- but it's going to generally take lesser time than Selection Sort.  In the best scenario, it takes only 1 step.

- ##### Merge Sort:
	- Divide the list into two halves and separately sort the left and the right half. Then merge the two lists by comparing each element from the two lists one-by-one in the order.
	- takes time $O(n \log n)$
	- Combine two lists A and B into C
		- If A is empty, copy B into C
		- If B is empty, copy A into C
		- Otherwise, compare first elements of A and B and move the smaller of the two to C. Repeat till A and B are exhausted.
	```Python
	def merge(A,B):
		(m,n) = (len(A), len(B))
		(C, i, j, k) = ([], 0, 0 ,0)
		
		while k < m+n: 
			if i == m: # checks is A is empty
				C.extend(B[j:])
				k = k + (n-j)
			
			elif j == n: # checks is B is empty
				C.extend(A[i:])
				k = k + (m-i)
			
			elif A[i] < B[j]:
				C.append(A[i])
				(i,k) = (i+1, k+1)
			
			else:
				C.append(B[j])
				(j,k) = (j+1, k+1)
		
		return C
	
	def mergesort(A):
		n = len(A)
		
		if n <= 1:
			return A
		
		L = mergesort(A[:n//2])
		R = mergesort(A[n//2:])
		
		B = merge(L,R)
		
		return B
	```

# <u>Week 3</u>
| **Algorithm**  | **Methodology**                                                                     | **Best case**   | **Average case** | **Worst case**      |
| -------------- | ----------------------------------------------------------------------------------- | --------------- | ---------------- | --------------- |
| Insertion Sort | insert each element in its right position                                           | $O(n)$          | $O(n^2)$         | $O(n^2)$        |
| Selection Sort | scan entire list and find the minimum                                               | $O(n^2)$        | $O(n^2)$         | $O(n^2)$        |
| Merge Sort     | divide the list, sort separately, then merge                                        | $O(n\log_2{n})$ | $O(n\log_2{n})$  | $O(n\log_2{n})$ |
| Quick Sort     | move smaller (larger) elements to left (right) of pivot, sort left and right halves | $O(n\log_2{n})$ | $O(n\log_2{n})$  | $O(n^2)$        |

- ##### Quicksort
	- Steps
		- Suppose median of $L$ is $m$
		- Move all values $\leq m$ to the left half of $L$ 
		- Recursively sort left and right halves
		- Recurrence: $T(n) = 2T(n/2) + n$; $T(n)$ is $O( n \log n)$
	- Instead of picking the median, just pick any value (called 'pivot')
	- Four segments: Pivot, Lower, Upper, Unclassified
		```Python
		def quicksort(L,l,r): # Sort L[l:r]
			if (r-l <= 1):
				return L
			
			(pivot, lower, upper) = (L[l], l+1, l+1)
			
			for i in range(l+1,r):
		
				if L[i] > pivot: # Extend upper segment
					upper += 1
		
				else: # Exchange L[i] with start of upper segment
					(L[i], L[lower]) = (L[lower], L[i])
					# shift both segments
					(lower, upper) = (lower+1, upper+1)
			
			# Move pivot between lower and upper
			(L[l], L[lower-1]) = (L[lower-1], L[l])
			lower -= 1
			# Recursive calls
			quicksort(L, l, lower)
			quicksort(L, lower+1, upper)
			return L
		```
	- worst case complexity: if pivot is maximum or minimum: $T(n)$ is $O(n^2)$
	 - but the average complexity is $O( n \log n)$; can be done by randomly choosing the pivot position instead of always picking the left-most or the right-most or the middle position

- **Stability** of sorting: when I sort on a column, it should not disturb the sorting on a previously sorted column
	- Mergesort can be customised to take care of stability; when merging, if you find two equal values, prefer to keep the order the same.

- ##### List
	- flexible length
	- typically a sequence of nodes;
		- to go to i-th position, start from the first and keep until i-th position
	- each node contains a value and points to the next node in the sequence![[Screenshot 2023-10-14 at 5.43.51 PM.png]]
	- easy to modify
	- Implementation
		```Python
		class Node:
			def __init__(self, v=None):
				self.value = v
				self.next = None
				return
			
			def isempty(self):
				if self.value == None:
					return True
				else:
					return False
			
			def append(self, v):
				if self.isempty():
					self.value = v
				
				elif self.next = None:
					self.next = Node(v)
				
				else:
					self.next.append(v)
				
				return
			
			def insert(self, v):
				if self.isempty():
					self.value = v
				
				new_node = Node(v)
				
				# Exchange values in self and new_node
				(self.value, new_node.value) = (new_node.value, self.value)
				
				# Switch links
				(self.next, new_node.next) = (new_node.next, self.next)
				
				return
			
			def delete(self, v):
				if self.isempty():
					return
				
				if self.value == v:
					self.value = None
					
					if self.next != None:
						self.value = self.next.value
						self.next = self.next.next
				
				else:
					if self.next != None:
						self.next.delete(v)
						if self.next.value == None:
							self.next = None
				
				return
		```
- ##### Array
	- fixed size, declared in advance
	- 'random' access
		- to go to i-th position, go directly to the i-th position
- Operations:
	- Exchange $A[i]$ and $A[j]$:
		- Arrays: constant time 
		- Lists: $O(n)$
	- Delete $A[i]$, insert $v$ after $A[i]$
		- Lists: constant time if we are at $A[i]$
		- Arrays: $O(n)$
- Lists in python are **not** implemented as flexible linked lists; they're implemented as arrays.
- to create an empty matrix in numpy, using an array of arrays
```Python
zero_matrix = np.zeros(shape=(3,3))
```
- numpy equivalent of 'range' function for lists: row2 = np.arange(5)

- ##### Dictionary
	- key-value pairs
	- take a key and map it to a position in array. This is called a Hash table, which is an array of size $n$ combined with a has function which maps keys to array values.
	- Hash Table
		- An array $A$ of size $n$ combined with a hash function $h$
		- $h$ maps keys to $\{0,1,\ldots,n-1\}$
		- Dealing with collisions (if there is already some value at the place that you're trying to put a value)
			- Open addressing (closed hashing)
				- probe a sequence of alternate slots in the same array;
				- this is why usually the hash table has more slots than are required
			- Open hashing
				- Each slot in the array point to a list of values
				- Insert into the list for the given slot


# <u>Week 4</u>
| Algorithm              | Methodology                                                               | Complexity                      | Remarks                                                  |
| ---------------------- | ------------------------------------------------------------------------- | ------------------------------- | -------------------------------------------------------- |
| Graph Colouring        | no two connected vertices have the same colour                            |                                 | any planar graph requires $\leq 4$ colours               |
| Vertex Cover           | minimum # of vertices that cover all edges                                |                                 |                                                          |
| Independent Set        | set of vertices such that no two are connected                            |                                 |                                                          |
| Matching               | set of edges such that no two edges share a vertex                        |                                 |                                                          |
| Breadth-First Search   | level-by-level                                                            | Mat: $O(n^2)$; List: $O(n+m)$ | Uses a queue; can find shortest path in # of edges       |
| Depth-First Search     | suspend search of parent and explore the child; then retrace              | Mat: $O(n^2)$; List: $O(n+m)$ | Uses a stack                                             |
| Connected Components** | count the number of BFS/DFS needed to explore all vertices                |                                 |                                                          |
| Detecting Cycles**     | BFS tree for undirected graphs; back-edge in DFS tree for directed graphs |                                 |                                                          |
| Topological Sorting    | start with 0 in-degree, remove it, update the in-degrees                  | Mat: $O(n^2)$; List: $O(n+m)$                                | works only for DAGs; can compute longest-path in a graph |

- Graph $G = (V,E)$:
	- $V$ --> set of vertices/nodes
	- $E$ --> set of edges
	- $E \subseteq V \times V$ — binary relation
	- **Directed Graphs**
		- $(v, v') \in E$ does not imply  $(v', v) \in E$
		- example: teacher-course graph![[Screenshot 2023-10-18 at 9.31.15 PM.png]]
	- **Undirected Graphs**
		- $(v, v') \in E$ iff  $(v', v) \in E$
		- $(v, v')$, $(v', v)$ are the same edges
		- example: friendship graph![[Screenshot 2023-10-18 at 9.31.30 PM.png]]
- Path: sequence of vertices connected by edges.
	- normally, does not visit a vertex twice; **walk** is a sequence that visits a vertex twice.
- Reachability
	- Vertex $v$ is **reachable** from vertex $u$ if there is a path from $u$ to $v$.
	- Connected graph: when any vertex is reachable from any other vertex.
- **Graph colouring**
	- Graph $G = (V,E)$, set of colours $C$
	- Colouring is a function $c : V \to C$ such that $(u,v) \in E \Rightarrow c(u) \neq c(v)$, i.e. if $(u,v)$ is an edge then the colour assigned to $u$ should not be the same as the colour assigned to $v$.
	- Four Colour Theorem: For any planar graph (i.e., no edge is crossing another edge), 4 colours suffice.
- **Vertex cover**
	- Minimum number of vertices that cover all the edges.
	- Subset of vertices such that every edge has one endpoint in the set.
- **Independent set**
	- Subset of vertices such that no two are connected by an edge.
- **Matching**
	- Subset $M \subseteq E$ of mutually disjoint edges; no two edges share any vertex.

- **Adjacency Matrix**
	- $V = \{0,1, \ldots, n-1\}$
	- Edges are pairs $(i,j)$, where $0 \leq i,j < n$;  and $i \neq j$, i.e., no self loops
	- Matrix $A$: rows and columns numbered $\{0,1, \ldots, n-1\}$
		- $A[i,j] = 1$ if $(i,j) \in E$ ![[Screenshot 2023-10-19 at 10.25.10 PM.png]]
	- **Degree** of a vertex $i$:
		- Undirected graph: number of edges incident on $i$
		- Directed graph: out-degree; and in-degree
	- Reachability:
		- Breadth-First Search: layer-by-layer; how many things can be reached in 1-step, 2-steps, and so on..
		- Depth-First Search: explore a path till it comes to an end and then backtrack
	- Adjacency list
		- shows only the edges that exist. Adjacency matrix has too many 0s.
		- generally stored as a <u>dictionary</u> with <u>keys</u> as vertices and <u>values</u> as list of vertices that are connected to the 'key-vertex'.
		- Adjacency requires less space.

- ### Breadth-First Search
	- One level at a time.
	- Each <u>visited</u> vertex has to be <u>explored</u> only once
	- Use a **queue** to keep a track of all visited vertices; FIFO
		```Python
		class Queue():
			def __init__(self):
				self.queue = []
			
			def addq(self, v):
				self.queue.append(v)
			
			def delq(self):
				v = None
				if not self.isempty():
					v = self.queue[0]
					self.queue = self.queue[1:]
				
				return v
			
			def isempty(self):
				return (self.queue == [])
			
			def __str__(self):
				return(str(self.queue))
		```
	- Exploring a vertex $i$:
		- For every edge $(i,j)$, if visited($j$) is False:
			- Set visited($j$) to True
			- Append $j$ to the queue
	- Code for BFS
		```Python
		def BFS(AMat, v):
			(rows, cols) = AMat.shape
			visited = {}
			
			for i in range(rows):
				visited[i] = False
			
			q = Queue()
			
			visited[v] = True
			q.addq(v)
			
			while (not q.isempty()):
				j = q.delq()
				
				# for every vertex that has an outgoing edge from j
				for k in neighbours(AMat, j): 
					if (not visited[k]):
						visited[k] = True
						q.addq(k)
			
			return visited
		```
	- Complexity
		- Assume $n$ vertices and $m$ edges.
		- If G is connected, $(n-1) \leq m \leq \frac{n(n-1)}{2}$ 
		- Sum of degrees $= 2m$
		- With adjacency matrix: $O(n^2)$
			- $n$ steps to initialise each vertex
			- $n$ steps to explore each vertex
		- With adjacency list: $O(n+m)$
			- $n$ steps to initialise each vertex
			- $2m$ steps (sum of degrees) to explore all vertices
		- if $m \ll n^2$, adjacency lists are much more efficient.
	- Path recording
		```Python
		def BFSListPath(AList, v):
			(visited, parent) = ({},{})
			for i in AList.keys():
				visited[i] = False
				parent[i] = -1
			
			q = Queue()
			
			visited[v] = True
			q.addq(v)
			
			while (not q.isempty()):
				j = q.delq()
				
				# parent allows you trace back the path
				for k in AList[j]:
					if not visited[k]:
						visited[k] = True
						parent[k] = j
						q.addq(k)
			
			return (visited, parent)
		```
	- Distance recording
		- Discovers shortest paths in terms of number of edges
		```Python
		def BFSListPath(AList, v):
			(level, parent) = ({},{})
			for i in AList.keys():
				level[i] = -1
				parent[i] = -1
			
			q = Queue()
			
			level[v] = 0
			q.addq(v)
			
			while (not q.isempty()):
				j = q.delq()
				
				# parent allows you trace back the path
				# level keeps a track of how many steps taken from root
				for k in AList[j]:
					if level[k] == -1:
						level[k] = level[j] + 1
						parent[k] = j
						q.addq(k)
			
			return (visited, parent)
		```

- ### Depth-First Search
	- Starting from a vertex $i$, visit an unexplored vertex $j$; then suspend the exploration of $i$ and explore $j$ instead. Continue until you reach a vertex with no unexplored neighbours. Backtrack to nearest suspended vertex.
	- Uses a **stack** to keep a track of visited vertices; LIFO
	- Implemented recursively
		```Python
		(visited, parent) = ({},{})
		
		def DFSInit(AMat): # Initialisation
			(rows,cols) = AMat.shape
			
			for i in range(rows):
				visited[i] = False
				parent[i] = -1
			return (visited, parent)
		
		def DFS(AMat, v):
			visited[v] = True
			
			for k in neighbours(AMat, v):
				if not visited[k]:
					parent[k] = v
					DFS(AMat, k)
			
			return (visited, parent)
		```


- #### Identifying connected components
	1. Start BFS/DFS from vertex 0
	2. Assign each visited vertex component number 0
	3. Pick the smallest unvisited vertex $j$ and repeat steps 1 & 2 and increase component number + 1.
	4. Repeat until all vertices are visited.
	```Python
	def Components(AList):
		component = {}
		for i in AList.keys():
			component[i] = -1
		
		(compid, seen) = (0,0)
		
		while seen <= max(AList.keys()):
			startv = min([i for i in AList.keys() if component[i] == -1])
			visited = BFSList(AList, startv)
			
			for i in visited.keys():
				if visited[i]:
					seen += 1
					component[i] = compid
			
			compid += 1
		
		return component
	```

- #### Detecting cycles
	- A walk that starts and ends at the same vertex
	- Does not repeat an edge: $i \to j \to i$ is not a cycle.
	- Simple cycle: only repeated vertices are at the start and the end.
	- ##### BFS tree
		- edges explored by BFS form a <u>tree</u>
		- one tree per component.
		- Any non-tree edge creates a cycle, e.g., red edges are explored by BFS and blue edges create a cycle                                                  ![[Screenshot 2023-10-20 at 10.59.17 PM.png]]
	- ##### DFS tree
		- Maintain a counter, initialised at 0.
		- Increment counter at each time we start (pre) and finish (post) exploring a vertex.![[Screenshot 2023-10-20 at 11.04.34 PM.png]]
		```Python
		(visited, pre, post) = ({}, {}, {})
		
		def DFSInitPrePost(AList):
			for i in AList.keys():
				visited[i] = False
				(pre[i], post[i]) = (-1, -1)
			
		return
		
		def DFSPrePost(AList, v, count):
			visited[v] = True
			pre[v] = count
			count += 1
			for k in AList[v]:
				if not visited[k]:
					count = DFSPrePost(AList, k, count)
			
			post[v] = count
			count += 1
			
			return count
		```
		- Undirected graphs: Non-tree edges generate a cycle.
		- Directed graphs:
			- <u>Forward edges</u>: an edge that goes from a vertex in the tree to another vertex which is below the first vertex.
			  An edge $(u,v)$ is a forward edge if $[pre(u), post(u)]$ contains $[pre(v), post(v)]$.
			- <u>Backward edges</u>: form cycles
			  An edge $(u,v)$ is a backward edge if $[pre(v), post(v)]$ contains $[pre(u), post(u)]$.
			- <u>Cross edges</u>: an edge that go across branches
			  An edge $(u,v)$ is a cross edge if $[pre(v), post(v)]$ and $[pre(u), post(u)]$ are disjoint.
		- Strongly connect components: vertices $i$ and $j$ are strongly connected if there is a path from $i$ to $j$ and a path from $j$ to $i$.

- #### Topological Sort
	- has to be a Directed Acyclic Graph
	- Every DAG can be topologically sorted![[Screenshot 2023-10-21 at 12.31.54 PM.png]]
	- Steps:
		1. List a vertex with no dependencies, i.e., with in-degree = 0.
		2. Remove the vertex with in-degree 0 from the DAG, and update the in-degree of all the vertices; Add the removed vertex into 'topologically sorted sequence'.
		3. Repeat Steps 1 & 2 until all vertices are listed.
	- Implementation:
		```Python
		def topsort(AMat): # Adjacency Matrix
			(rows, cols) = AMat.shape
			indegree = {}
			topsortlist = {}
			
			for c in range(cols):
				indegree[c] = 0
				for r in range(rows):
					if AMat[r][c] == 1:
						indegree[c] += 1
			
			for i in range(rows):
				j = min([k for k in range(cols) if indegree[k] == 0])
				topsortlist.append(j)
				indegree[j] -= 1
				for k in range(cols):
					if AMat[j,k] == 1:
						indegree[k] -= 1
			
			return topsortlist
		
		def topsortList(AList): # Adjacency List
			(indegree, topsortlist) = ({}, [])
			
			for c in AList.keys():
				indegree[c] = 0
			for c in AList.keys():
				for v in AList[c]:
					indegree[v] += 1
			
			zerodegreeq = Queue()
			for u in AList.keys():
				if indegree[u] == 0:
					zerodegreeq.addq(u)
			
			while not zerodegreeq.isempty():
				j = zerodegreeq.delq()
				topsortlist.append(j)
				indegree[j] -= 1
				
				for k in AList[j]:
					indegree[k] -= 1
					if indegree[k] == 0:
						zerodegree.addq(k)
			
			return topsortlist
		```
	-  Longest Path:
		- $\text{longest-path-to}(i) = 1 + max\{\text{longest-path-to}(j)\ |\ (j,i) \in E\}$
		- Compute longest path in topological ordering.
		```Python
		def topsortList(AList): # Adjacency List
			(indegree, lpath) = ({}, {})
			
			for c in AList.keys():
				(indegree[c], lpath[c]) = (0, 0)
			for c in AList.keys():
				for v in AList[c]:
					indegree[v] += 1
			
			zerodegreeq = Queue()
			for u in AList.keys():
				if indegree[u] == 0:
					zerodegreeq.addq(u)
			
			while not zerodegreeq.isempty():
				j = zerodegreeq.delq()
				indegree[j] -= 1
				
				for k in AList[j]:
					indegree[k] -= 1
					lpath[k] = max(lpath[k], lpath[j] + 1)
					if indegree[k] == 0:
						zerodegreeq.addq(k)
			
			return lpath
		```


# <u>Week 5</u>
| **Algorithm**  | **Use Case**                | **Methodology**                                                            | **Complexity**                      | 
| -------------- | --------------------------- | -------------------------------------------------------------------------- | ----------------------------------- |
| Dijkstra's     | Single-source shortest path | pick shortest path at every vertex; only for <u>non-negative weights</u>   | $O(n^2)$                            |
| Bellman-Ford   | Single-source shortest path | update shortest path iteratively n-1 times; allows <u>negative weights</u> | $O(n^3)$ for Mat; $O(n^2)$ for List |
| Floyd-Warshall | All-pairs shortest path     | Transitive Closure; uses <u>SP matrix</u>                                  | $O(n^3)$                            |
| Prim's         | Minimum Cost Spanning Tree  | Similar to Dijkstra; greedy algorithm                                      | $O(n^2)$                            |
| Kruskal's      | Minimum Cost Spanning Tree  | process edges in ascending order                                           | $O(n^2)$                            |

- Weighted graph $G = (V,E), W \colon E \to \mathbb{R}$![[Screenshot 2023-10-25 at 7.09.59 PM.png]]

- ### Dijkstra's Algorithm
	- Single Source shortest path; works only with non-negative weights
	- Each time a new vertex is visited, update the expected cost of its neighbours.
	- Each new shortest path we discover extends an earlier one.
	- <u>Greedy strategy</u>: forward-thinking strategy where we keep making a local decision and never go back on it.
	- Implementation
		```Python
		def dijkstra(WMat, s):
			(rows, cols, x) = WMat.shape
			# infinity = largest weight and multiply with number of vertices 
			infinity = np.max(WMat) * rows + 1
			(visited, distance) = ({}, {})
			
			for v in range(rows):
				(visited[v], distance[v]) = (False, infinity)
			
			distance[s] = 0
			for u in range(rows):
				nextd = min(distance[v] for v in range(rows) if not visited[v])
				nextvlist = [ v for v in range(rows) if (not visited[v]) and distance[v] == nextd]
				
				if nextvlist == []:
					break
				
				nextv = min(nextvlist)
				visited[nextv] = True
				for v in range(cols):
					if WMat[nextv, v, 0] == 1 and (not visited[v]):
						distance[v] = min(distance[v], distance[nextv] + WMat[nextv, v, 1])
			
			return distance
		```
	- Complexity:
		- Setting `infinity` takes $O(n^2)$ time
		- Main loop also takes $O(n^2)$ time.

- ### Bellman-Ford Algorithm
	- Single-source shortest path; works with negative weights
	- negative cycles are not allowed, therefore shortest route to every vertex is a path, no loops.
	- Repeatedly update shortest distance to each vertex based on shortest distance to its neighbours.
	- <u>can detect if there is a negative cycle</u> by checking if the shortest distances stabilise after iterating $n-1$ times, $n$ being the number of vertices.
	- complexity: 
		- Adjacency matrix takes $O(n^3)$ time.
		- Adjacency list takes $O(n^2)$ time.
	- Implementation:
		```Python
		def bellmanford(WMat, s): # FOR ADJACENCY MATRIX
			(rows, cols, x) = WMat.shape
			infinity = np.max(WMat) * rows + 1
			distance = {}
			
			for v in range(rows):
				distance[v] = infinity
			
			distance[s] = 0
			
			for i in range(rows):
				for u in range(rows):
					for v in range(cols):
						if WMat[u,v,0] == 1:
							distance[v] = min(distance[v], distance[u] + WMat[u,v,1])
			
			return distance
		
		
		def bellmanfordList(WList, s): # FOR ADJACENCY LIST
			infinity = 1 + len(WList.keys()) * max([d for u in WList.keys() for (v,d) in WList[u]])
			
			distance = {}
			for v in WList.keys():
				distance[v] = infinity
			
			distance[s] = 0
			
			for i in WList.keys():
				for u in WList.keys():
					for (v,d) in WList[u]:
						distance[v] = min(distance[v], distance[u] + d)
			
			return distance
		```

- ### Floyd-Warshall Algorithm
	- One way: run Dijkstra or Bellman-Ford from each vertex.
	- <u>can be used to detect negative cycle</u> by checking if any diagonal entry has a negative weight, i.e. path from a vertex to itself costs negative.
	- ##### Transitive Closure
		- Adjacency matrix $A$ represents paths of length of $1$ 
		- Matrix multiplication, $A^2 = A \times A$
			- $A^2[i,j] = 1$ if there is a path of length 2 from $i$ to $j$
			- For some $k$, $A[i,k] = A[k,j] = 1$
		- $A^{l+1} = A^l \times A$
			- $A^{l+1}[i,j] = 1$ if there is a path of length $l+1$ from $i$ to $j$
			- For some $k$, $A^l[i,k] = A[k,j] = 1$
		- $A^{+} = A + A^2 + \cdots + A^{n-1}$
	- Steps:
		1. Let $SP^k[i,j]$ be the length of the shortest path from $i$ to $j$ via vertices $\{0,1,\ldots,k-1 \}$
		2. $SP^0[i,j] = W[i,j]$
			- No intermediate vertices, shortest path is the weight of direct edge
			- Assume $W[i,j] = \infty$ if $(i,j) \notin E$
		3. $SP^{k+1}[i,j]$ is the minimum of
			- $SP^k[i,j]$                               Shortest Path using only $\{0,1,\ldots,k-1 \}$
			- $SP^k[i,k] + SP^k[k,j]$             Combine shortest path from $i$ to $k$ and $k$ to $j$
		4. $SP^n[i,j] = 1$ is the length of the shortest path overall from $i$ to $j$
			- intermediate vertices lie in $\{0,1,\ldots,n-1 \}$
	- Example:
		- $SP^1$ has no impact because $0$ vertex has no incoming edge.![[Screenshot 2023-10-25 at 9.38.20 PM.png]]
		- $SP^2$ allows vertices $0, 2, \text{and}\ 6$ to go to vertex $5$ via vertex $1$ ![[Screenshot 2023-10-25 at 9.39.09 PM.png]]
		- $SP^3$ allow vertex $5$ to go to vertices $1, 3, \text{and}\ 5$ via vertex $2$![[Screenshot 2023-10-25 at 9.43.00 PM.png]]
	- <u>Implementation</u>
		```Python
		def floydwarshall(WMat):
			(rows, cols, x) = WMat.shape
			infinity = np.max(WMat) * rows * rows + 1
			
			SP = np.zeros(shape = (rows, cols, cols+1)) 
			
			for i in range(rows):
				for j in range(cols):
					if WMat[i,j,0] == 1:
						SP[i,j,0] = WMat[i,j,1]
			
			for k in range(1, cols + 1):
				for i in range(rows):
					for j in range(cols):
						SP[i,j,k] = min(SP[i,j,k-1], SP[i,k-1,k-1] + SP[k-1,j,k-1])
			
			return SP[:,:,cols]
		```

- ### Minimum Cost Spanning Tree
	- minimally connected acyclic graph.
	- A tree of $n$ vertices has $n-1$ edges.
	- Adding an edge to a tree must create a cycle.
	- Every pair of vertices is connected by a unique path.
	- #### Prim's Algorithm
		- Start from any vertex and then grow the tree by incrementally picking the least edge that is not forming a cycle.
		- for time complexity $O(n^3)$:
			```Python
			def primlist(WList):
				infinity = 1 + max([d for u in WList.keys for (v,d) in WList[u]])
				(visited, distance, TreeEdges) = ({},{},{})
				
				for v in WList.keys():
					(visited[v], distance[v]) = (False, infinity)
				
				visited[0] = True
				for (v,d) in WList[0]:
					distance[v] = d
				
				for i in WList.keys():
					(mindist, nextv) = (infinity, None)
					
					for u in WList.keys():
						for (v,d) in WList[u]:
							if visited[u] and (not visited[v]) and d < mindist:
								(mindist, nextv, nexte) = (d, v, (u,v))
					
					if nextv is None:
						break
					visited[nextv] = True
					TreeEdges.append(nexte)
					for (v,d) in WList[nextv]:
						if not visited[v]:
							distance[v] = min(distance[v], d)
				
				return TreeEdges
			```
		- for time complexity $O(n^2)$: (very similar to Dijkstra's except the distance updation)
			```Python
			def primlist2(Wlist):
				infinity = 1 + max([d for u in WList.keys for (v,d) in WList[u]])
				(visited, distance, nbr) = ({},{},{})
				
				for v in WList.keys():
					(visited[v], distance[v], nbr[v]) = (False, infinity, -1)
				
				visited[0] = True
				for (v,d) in WList[0]:
					(distance[v], nbr[v]) = (d, 0)
				
				for i in range(1, len(WList.keys())):
					nextd = min([distance[v] for v in WList.keys() if not visited[v]])
					nextvlist = [v for v in WList.keys() if (not visited[v]) and distance[v] == nextd]
				
					if nextvlist = []:
						break
					
					nextv = min(nextvlist)
					visited[nextv] = True
					for (v,d) in WList[nextv]:
						if not visited[v]:
							(distance[v], nbr[v]) = (min(distance[v], d), nextv)
			```
	- #### Kruskal's Algorithm
		- Process edges in ascending order, and include edge if it does not create a cycle.
		- has time complexity $O(n^2)$
			```Python
			def kruskal(WList):
			    
			    (edges, component, TE) = ([], {}, [])
			    
			    for u in WList.keys():
			        
			        edges.extend([(d,u,v) for (v,d) in WList[u]])
			        component[u] = u
			        
			    edges.sort()
			    
			    for (d,u,v) in edges:
			        
			        if component[u] != component[v]:
			            TE.append((u,v))
			            c = component[u]
			            
			            for w in WList.keys():
			                if component[w] == c:
			                    component[w] = component[v]
			                    
			    return TE
			```


# <u>Week 6</u>
- ### Union-Find Data Structure
	- Improvement of <u>Kruskal's</u> algorithm
	- <u>Brief</u>
		- Set $S$ partitioned into components $\{ C_1, C_2, \ldots, C_k \}$. Each $s \in S$ belongs to exactly one $C_j$
		- `MakeUnionFind(S)` — set up singleton components $\{s\}$ for each $s \in S$
		- `Find(s)` — return the component containing $s$
		- `Union(s, s')` — merge components containing $s, s'$
	- A better implementation (with Complexity $O(\log m)$):
		```Python
		def MakeUnionFind(S):
			for i in S:
				Component[i] = i # for all i
				(Members[i], Size[i]) = ([i],1) # for all i
		
		def Find(i):
			return Component[i]
		
		def Union(i,j):
			old_component = min(Size[Component[i]], Size[Component[j]])
			new_component = max(Size[Component[i]], Size[Component[j]])
			# Always merging the smaller component into large one
			for k in Members[old_component]:
				Component[k] = new_component
				Members[new_component].append(k)
				Size[new_component] += 1
		```

- ### Priority Queues
	- Used in Prim's and Dijkstra's algorithms.
	- need to maintain a collection of items with priorities to optimise:
		- `delete_max()` identifies and removes the item with the highest priority; need not be unique
		- `insert()` add a new item to the collection
	- ###### Moving to two dimensions
		- Assume $N$ processes enter/leave the queue.
		- total time takes $O(N \sqrt{N})$
		- Maintain $\sqrt{N} \times \sqrt{N}$ array with each row in sorted order.![[Screenshot 2023-11-02 at 9.43.05 PM.png]]
		- how to do `insert()` with two-dimensions
			- takes time $O(\sqrt{N})$
			- keep track of length of each row
			- insert an element into the first row that has space     ![[Screenshot 2023-11-02 at 9.44.34 PM.png]]
			  inserting $15$:                             ![[Screenshot 2023-11-02 at 9.47.52 PM.png]]
		- how to do `delete_max()` with two dimensions
			- takes time $O(\sqrt{N})$
			- max in each row is the last element
			- pull out the max among all the last elements.

- #### Binary trees
	- Each node has up to 2 children. (left and right; order is important)
	- Each node has a unique parent. 
	- Leaf node — no children
	- Size — number of nodes
	- Height — number of levels![[Screenshot 2023-11-02 at 10.28.07 PM.png]]

- ### Heap
	- binary tree filed level by level, left to right
	- value at each node is at least as big as its children
	- root always has the largest value
	- Heap doesn't have any properties about the relative values of the two children. Heap only talks about properties between levels, not left-right.
	- how to implement `insert()`
		- insert the element and exchange with the parent until it's placed in the correct order.
		- time will be proportional to the height of the tree.
		- Number of nodes at level $j$ is $2^j$
		- $\text{Size} = 2^{\text{height}}$; $\text{height} = \log \text{size}$
		- complexity of `insert()` is $O( \log N)$
	- how to implement `delete_max()`
		- maximum value is always at the root.
		- rest of the nodes have to be adjusted.
		- delete the rightmost node at the lowest level, move the 'homeless' value to the root, and then fix the ordering by swapping with the bigger child of the two children.
		- complexity of `delete_max()` is $O( \log N)$
	- Implementation
		- store the values in a list. `H = [h0, h1, h2,.., hn-1]`
		- number the nodes from top to bottom, left to right.
		- Children of `H[i]` are at `H[2*i + 1]` and `H[2*i + 2]`
		- Parent of `H[i]` is at `H[(i-1)//2]`, for `i > 0`![[Screenshot 2023-11-02 at 10.49.44 PM.png]]
	- Building a heap
		- build a heap list given a list $L = [v_0, v_1,\ldots, v_N]$
		- $\text{mid} = len(L) // 2$
		- leaf nodes are always compliant because they don't have children, and `L[mid:]` has only leaf nodes.
		- Starting from the last level (leaf nodes), fix heap property downwards for second last level. Iterate until root. 
		- Can be done in $O(N)$ time.
		- Code:
		```Python
		def max_heapify(heap, n, i):
		    
		    l = 2*i + 1
		    r = 2*i + 2
		    largest = i
		    
		    if (l < n) and heap[l] > heap[largest]:
		        largest = l
		    
		    if (r < n) and heap[r] > heap[largest]:
		        largest = r
		        
		    if largest != i:
		        heap[i], heap[largest] =  heap[largest], heap[i]
		        max_heapify(heap, n, largest)
		    
		    return None
		
		
		def min_max(arr):
		    n = len(arr)
		    
		    for i in range(n//2 -1, -1, -1):
		        max_heapify(arr, n, i)
		```
	- #### Dijkstra using Heap
		- Use a min-heap where $\text{parent node} <= \text{child node}$
		- Min-heap stores the distance to each vertex in the original graph. To keep a track of which node of heap corresponds to which vertex of graph, maintain two dictionaries:
			- $\text{Vertices} = {0, 1, \ldots, n-1}$ and $\text{Heap positions} = {0, 1, \ldots, n-1}$
			- $\text{VtoH}$ maps vertices to heap positions
			- $\text{HtoV}$ maps heap positions to vertices
		- takes time $O(n \log n)$
	- #### Sorting using Heap
		- cleverer way of Selection_sort

- ### Binary search tree
	- Like a heap but a node could have only a right child; whether it's a right child or left child is important.
	- unlike heap, binary search tree talks about the values in left-right also.
	- For each node with value $v$, all values in the left subtree are $< v$ and all values in the right subtree are $> v$. No duplicate values allowed. Example:![[Screenshot 2023-11-04 at 12.49.27 AM.png]]
	- Implementation
		- Each node has a value and pointers to its children.
		- Add a frontier with empty nodes. leaf node points to empty nodes![[Screenshot 2023-11-04 at 12.56.05 AM.png]]
	- Code:
		```Python
		class Tree:
		
			# Constructor
			def __init__(self, initval = None):
				self.value = initval
				if self.value:
					self.left = Tree()
					self.right = Tree()
					self.height = 1
				else:
					self.left = None
					self.right = None
					self.height = 0
			
			# Only empty node has value None
			def isempty(self):
				return self.value == None
			
			# Leaf nodes have both children empty
			def isleaf(self):
				return ((self.value != None) and (self.left.isempty()) and (self.right.isempty()))
			
			# Inorder traversal
			def inorder(self):
				if self.isempty():
					return([])
				else:
					return (self.left.inorder() + [self.value] + self.right.inorder())
			
			# Postorder traversal
			def postorder(self):
				if self.isempty():
					return([])
				else:
					return (self.left.postorder() + self.right.postorder() + [self.value])
			
			# Preorder traversal
			def preorder(self):
				if self.isempty():
					return([])
				else:
					return ([self.value] + self.left.preorder() + self.right.preorder())
			
			# Display Tree as a string
			def __str__(self):
				return str(self.inorder())
			
			# Check if value v occurs in tree
			def find(self, v):
				if self.isempty():
					return False
					
				if self.value == v:
					return True
					
				if v < self.value:
					return self.left.find(v)
					
				if v > self.value:
					return self.right.find(v)
			
			# Find minimum value
			def minval(self):
				if self.left.isempty():
					return self.value
				else:
					return self.left.minval()
			
			# Find maximum value
			def maxval(self):
				if self.right.isempty():
					return self.value
				else:
					return self.right.maxval()
			
			# Insert a value
			def insert(self, v):
				if self.isempty():
					self.value = v
					self.left = Tree()
					self.right = Tree()
				if self.value == v:
					return
				if v < self.value():
					self.left.insert(v)
					return
				if v > self.value():
					self.right.insert(v)
					return
			
			# Convert leaf node to empty node
			def makeempty(self):
				self.value = None
				self.left = None
				self.right = None
				return
			
			# Promote left child
			def copyleft(self):
				self.value = self.left.value
				self.right = self.left.right
				self.left = self.left.left
				return
			
			# Promote right child
			def copyright(self):
				self.value = self.right.value
				self.left = self.right.left
				self.right = self.right.right
				return
			
			# Delete a value
			def delete(self, v):
				if self.isempty():
					return
				
				if v < self.value():
					self.left.delete(v)
					return
				if v > self.value():
					self.right.delete(v)
					return
				
				if v == self.value:
					if self.isleaf():
						self.makeempty()
						
					elif self.left.isempty():
						self.copyright()
						
					elif self.right.isempty():
						self.copyleft()
						
					else:
						self.value = self.left.maxval() # take max val from left 
						self.left.delete(self.left.maxval()) # delete max val from left
		```


# <u>Week 7</u>
- Search trees have worst-case complexity the same as the height of the tree. Balanced trees have height $\log n$. So balanced trees have worst-case complexity $O(\log n)$
- ### Height balanced trees:
	- `self.height()` — number of nodes on longest path from root to leaf
		- $0$ for empty tree
		- $1$ for treen with only a root node
		- $1 + \max$ of heights of left and right subtrees, in general
	- `self.left.height()` and `self.right.height()` should differ at most 1
	- general strategy to build the smallest balanced tree of height $h$:
		- smallest balanced tree of height $h-1$ as left subtree
		- smallest balanced tree of heigh $h-2$ as right subtree![[Screenshot 2023-11-07 at 11.35.36 PM.png]]
	- $S(h)$, size of smallest heigh-balances tree as height $h$:
		- $S(h) = 1 + S(h-1) + S(h-2)$
		- Fibonacci sequence grows exponentially
	- Slope of a node: `self.left.height()` $-$ `self.right.height()`
	- Re-balancing the tree:
		- Left rotation: converts. Promotes the 'diamond' node to be the root node as opposed to the 'circle' node. Moves the "L" sub-tree to the right subtree of 'circle' node. Rotation doesn't always fix the tree![[Screenshot 2023-11-07 at 11.45.53 PM.png]]
	- Rotation implementation
		```Python
		class Tree:
		
			def leftrotation(self):
				v = self.value
				vr = self.right.value
				tl = self.left
				trl = self.right.left
				trr = self.right.right
				
				newleft = Tree(v)
				newleft.left = tl
				newleft.right = trl
				
				self.value = vr
				self.right = trr
				self.left = newleft
				
				return
			
			def rightrotation(self):
				v = self.value
				vl = self.left.value
				tr = self.right
				tlr = self.left.right
				tll = self.left.left
				
				newright = Tree(v)
				newright.left = tlr
				newright.right = tr
				
				self.value = vl
				self.right = newright
				self.left = tll
			
			def rebalance(self):
				if self.left == None:
					hl = 0
				else:
					hl = self.left.height
				
				if self.right == None:
					hr = 0
				else:
					hr = self.right.height
				
				if hl - hr > 1:
					if self.left.left.height > self.right.right.height:
						self.rightrotation()
					if self.left.left.heigh < self.right.right.height:
						self.left.leftrotation()
						self.righrotation()
					self.updateheight()
				
				if hl - hr < -1:
					if self.right.left.height < self.right.right.height:
						self.leftrotation()
					if self.right.left.height > self.right.right.height:
						self.right.rightrotation()
						self.leftrotation()
					self.updateheigh()
			
			def updateheight(self):
				if self.isempty():
					return
				else:
					self.left.updateheight()
					self.right.updateheight()
					self.height = 1 + max(self.left.height, self.right.height)
		```
	- Rebalancing using rotation (where root has slope $+2$)
		- For slope $\{0,1\}$: rotate right at 'circle' node![[Screenshot 2023-11-08 at 12.10.26 AM.png]]
		- For slope $-1$: 
			- Expand $R$ node![[Screenshot 2023-11-08 at 12.13.52 AM.png]]
			- Rotate left at 'diamond' node
			- Rotate left at 'circle' node![[Screenshot 2023-11-08 at 12.15.07 AM.png]]
	- need to maintain `self.height` for each node and update the height every time a change is made.
```Python
class Tree:
	
	def insert(self, v):
		if self.isempty():
			self.value = v
			self.left = Tree()
			self.right = Tree()
			self.height = 1
		
		if self.value == v:
			return
		
		if v < self.value:
			self.left.insert(v)
			self.left.rebalance()
			self.height = 1 + max(self.left.height, self.right.height)
			return
		
		if v > self.value:
			self.right.insert(v)
			self.right.rebalance()
			self.height = 1 + max(self.left.height, self.right.height)
			return
	
	def delete(self, v):
		if v < self.value:
			self.left.delete(v)
			self.left.rebalance()
			return
		
		if v > self.right:
			self.right.delete(v)
			self.right.rebalance()
			return
		
		if v == self.value:
			if self.isleaf():
				self.makeempty()
			elif self.left.isempty():
				self.copyright()
			elif self.right.isempty():
				self.copyleft()
			else:
				self.value = self.left.maxval()
				self.left.delete(self.left.maxval())
			return
```

- #### Greedy algorithm for interval scheduling
	- <u>problem</u>: different teachers want to book the classroom. Slot for instructor $i$ starts at $s(i)$ and finishes at $f(i)$. Slots may overlap, so not all bookings can be honoured. Choose a subset of bookings to maximise the number of teachers who get to use the room.
	- solution: greedy strategy —> choose the earliest finish time.
	- $B$ is the set of bookings. $A$ is the set of accepted bookings. 
		- While $B$ is not empty:
			- Pick $b \in B$ with earliest finishing time
			- Add $b$ to $A$
			- Remove from $B$ all bookings that overlap with $b$
	- Implementation:
		- Sort $n$ bookings by finish time — $O(n \log n)$
		- Record start and finish times in dictionary
			- $S[i]$ is start time time of request $i$
			- $F[i]$ is finish time time of request $i$
		- Add first booking to $A$
		- After adding booking $j$ to $A$, find the smallest $r$ with $S[r] > F[j]$ — $O(n)$

- #### Greedy algorithm for minimising lateness
	- <u>problem</u>: users need to use a printer. User $i$'s item takes $T(i)$ to print. User $i$ has a deadline $D(i)$. Each user will get access to the printer but may not finish before deadline. Start time is not pre-defined.
	- Assuming user $i$ will start at time $S(i)$, they finish at time $F(i)\ \text{where}\ F(i) = S(i) + T(i)$
	- User $i$ is late by $L(i) = \begin{cases} 0 & \text{if}\ D(i) \geq F(i) \\ F(i) - D(i) & \text{if}\ D(i) < F(i)  \end{cases}$
	- minimise the maximum lateness $$= \max_i L(i)$$
	- solution: greedy strategy —> choose the earliest deadline.
	- renumber the jobs so that they are sorted by deadline.$$D(1) \leq D(2) \leq \cdots \leq D(n) $$

- #### Greedy algorithm: Huffman Coding
	- Binary encoding: fixed-length encoding i.e., every 5 digits correspond to a number.
	- A more efficient way of encoding is to use variable length encoding, and use shorter digit lengths for alphabets that occur with a higher frequency.
	- <u>Prefix codes</u>
		- Encoding is such that encoding of $x$, $E(x)$, is not a prefix of $E(y)$ for any $x, y$
		- NOT example of prefix encoding: In morse code, $E(e) = 0$ is a prefix of $E(a) = 01$
		- Example of prefix code![[Screenshot 2023-11-08 at 6.01.14 PM.png]]
		- Decode: $0\ 0\ 1\ 0\ 0\ 0\ 0\ 0\ 1\ 1\ 1\ 0\ 1$![[Screenshot 2023-11-08 at 6.03.00 PM.png]]
	- Optimal prefix codes
		- measure frequency $f(x)$ of each letter. $A = \{ x_1, x_2, \ldots, x_m \}$; $f(x)$ is 'probability' that next letter is $x$
		- In a message with $n$ symbols, each letter $x$ occurs $n \cdot f(x)$ times.
		- Each $x$ encoded as $E(x)$ with length $|E(x)|$ , then total message length: $$\sum_{x \in A} n \cdot f(x) \cdot |E(x)|$$
		- Given a set of letters $A$ and frequencies $f(x)$ for each $x$, minimise $ABL(A)$ — Average Bits per Letter to produce the most efficient prefix code possible ![[Screenshot 2023-11-08 at 6.18.56 PM.png]]
		- encoding can be represented as binary trees. Letters at the leaves. Path to leaf — $0$ is left, and $1$ is right.![[Screenshot 2023-11-08 at 8.21.55 PM.png]]
		- <u>Full tree</u>: each node has $0$ or $2$ children
		- letters sitting at higher level have higher frequency.
		- ##### Claims:
			1. Any optimal prefix code produces a full tree.
			2. In an optimal tree, if leaf labelled $x$ is at a smaller depth than leaf labelled $y$, $f(x) \geq f(y)$.
			3. In an optimal tree, for any leaf at maximum depth, its sibling is also a leaf $x$.
	- #### Huffman's algorithm
		- starting with a frequency table, combine the two lowest frequencies iteratively until only two nodes are left.![[Screenshot 2023-11-08 at 8.31.43 PM.png]]
		- Then repeatedly split compound leaves to get a tree like this:![[Screenshot 2023-11-08 at 8.33.30 PM.png]]
		- Implementation:
			- At each recursive step, extract letter with minimum frequency and replace by composite letter with combined frequency.
			- Use heap to maintain frequencies, complexity of Huffman algorithm: $O(k \log k)$


# <u>Week 8</u>
- ### Divide and Conquer
	- break up a problem into disjoint subproblems; combine these subproblem solutions efficiently
	- Examples: Merge sort; Quicksort

- ##### Recommender systems
	- Identify people who share your likes and dislikes; recommend items that they like
	- Comparing rankings
		- you and your friend rank 5 movies: {A, B, C, D, E}
		- your ranking: D, B, C, A, E
		  friend's ranking: B, A, C, D, E
		- measuring similarity in the ranking:
		- <u>Inversions</u>: pair of movies ranked in opposite order (e.g. you rank D above D, the friend ranks B above D)
		- number of inversions ranges from $0$ to $\frac{n(n-1)}{2}$ —> measure of dissimilarity
	- Counting inversions
		- Your ranking: D, B, C, A, E
		  D = 1, B = 2, C = 3, A = 4, E = 5
		- Friend's ranking: B, A, C, D, E
		  = 2, 4, 3, 1, 5
		- in the order {2, 4, 3, 1, 5}; an inversion is a pair $(i,j), i<j,\ \text{where}\ j\ \text{appears before}\ i$
			- Inversions: $(1,2), (1,4), (1,3), (3,4)$
	- Friend's permutation is $i_1, i_2, \ldots, i_n$
		- divide into two lists
		  $L = [i_1, i_2, \ldots, i_n]$
		  $R = [i_{n/2+1}, i_{n/2+2}, \ldots, i_n]$
		- recursively count inversions in $L$ and $R$
		- add inversions across boundary between $L$ and $R$, i.e., $i \in L, j \in R, i>j$
			- count inversion while merging in merge sort
				- if we add $i_m$ from $R$ to the output, $i_m$ is smaller than elements currently in $L$
				- $i_m$ is hence inverted with respect to elements currently in $L$
				- Add current size of $L$ to inversion count
	```Python
	def mergeAndCount(A,B):
		(m,n) = (len(A), len(B))
		(C, i, j, k, count) = ([], 0, 0 ,0, 0)
		
		while k < m+n: 
			if i == m: # checks if A is empty
				C.extend(B[j:])
				k = k + (n-j)
			
			elif j == n: # checks if B is empty
				C.extend(A[i:])
				k = k + (m-i)
			
			elif A[i] < B[j]:
				C.append(A[i])
				(i,k) = (i+1, k+1)
			
			else:
				C.append(B[j])
				(j,k, count) = (j+1, k+1, count + (m-i))
		
		return C, count
	
	def sortAndCount(A):
		n = len(A)
		
		if n <= 1:
			return A, 0
		
		L, countL = sortAndCount(A[:n//2])
		R, countR = sortAndCount(A[n//2:])
		
		B, countB = mergeAndCount(L,R)
		
		total_inversions = countL + countR + countB
		return B, total_inversions
	```

- ##### Closest pair of points
	- split the points into two halved by vertical line; recursively compute closest pair in each half; compare shortest distance in each half to shortest distance across the dividing line
	- Given $n$ points $P = \{ p_1, p_2, \ldots, p_n \}$, compute 
		- $P_x$ which is $P$ sorted by $x$-coordinate
		- $P_y$ which is $P$ sorted by $y$-coordinate
	- Divide $P$ by vertical line into equal size $Q, R$
		- $Q_x$ is first half of $P_x$, and $R_x$ is second half of $P_x$
		- Let $x_R$ be the smallest $x$ coordinate in $R$
		- for $p \in P_y$ if $x$ coordinate of $p < x_R$, move $p$ to $Q_y$ else $R_y$
	- recursively compute $ClosestPair(P_x, P_y)$
		- split $(P_x,P_y)$ as $(Q_x,Q_y)$,$(R_x,R_y)$
		- compute $ClosestPair(Q_x, Q_y)$ and $ClosestPair(R_x, R_y)$
	- combine solutions
		- Let $d_Q, d_R$ be smallest distances in $Q, R$, respectively
		- Set $\delta = \min(d_Q, d_R)$
		- sufficient to consider points within distance $\delta$ on either side of the separator ![[Screenshot 2023-11-14 at 4.35.17 PM.png]]
		- Divide the distance $\delta$ band into boxes of side $\frac{\delta}{2}$. Any point within distance $\delta$ must lie in a $4 \times 4$ neighbourhood of boxes [[Screenshot 2023-11-14 at 4.42.00 PM.png]]
		- From $Q_y, R_y$, extract $S_y$, points in $\delta$ band sorted by $y$. Scan $S_y$ from bottom to top, comparing each $p$ with next $15$ points in $S_y$
		- pseudocode
		```Python
		def ClosestPair(Px, Py):
			if len(Px) <= 3:
				compute pairwise distances
				return closest pair and distance
			
			Construct (Qx, Qy), (Rx,Ry) # using midpoint in Px
			
			(q1, q2, dQ) = ClosestPair(Qx, Qy)
			(r1, r2, dR) = ClosestPair(Rx, Ry)
			
			Construct Sy from Qy, Ry
			Scan Sy to find (s1, s2, dS)
			
			return (q1, q2, dQ), (r1, r2, dR), (s1, s2, dS)
			depending on which of dQ, dR, dS is minimum
		```
		- Actual code:
		```Python
		def getDist_btw(p1, p2):
			
			x2 = (p1[0] - p2[0]) ** 2
			y2 = (p1[1] - p2[1]) ** 2
			
			return round((x2 + y2) ** (1/2), 2)
		
		def bruteforceDist(Points):
			min_d = None
			
			for i, point in enumerate(Points[:-1]):
				
				for point2 in Points[i+1:]:
					
					d = getDist_btw(point, point2)
					
					if min_d:
					
						if d < min_d:
							min_d = d
							closest = [point, point2]
					else:
						min_d = d
						closest = [point, point2]
						
			return closest, min_d
		
		def getLyRy(PY, min_rx):
			
			(Ly , Ry) = ([] , [])
			
			for point in PY:
				
				if point[0] < min_rx:
					Ly.append(point)
				
				else:
					Ry.append(point)
			
			return Ly, Ry
		
		
		def closestpair(PX, PY):
			
			n = len(PX)
			
			if n <=3:
				closest, min_d = bruteforceDist(PX)
				return closest, min_d
			
			else:
		
				Lx = PX[:n//2]
				Rx = PX[n//2:]
				
				Ly , Ry = getLyRy(PY, Rx[0][0])
				
				lpoints, d_l = closestpair(Lx, Ly)
				rpoints, d_r = closestpair(Rx, Ry)
				
				if d_l < d_r:
					min_points , delta = lpoints, d_l
				else:
					min_points , delta = rpoints, d_r
					
				
				Sy = []
				for point in PY:
					if abs(point[0] - Rx[0][0]) < delta:
						Sy.append(point)
				
				if len(Sy) > 1:
					
					min_S , d_s = [Sy[0],Sy[1]] , getDist_btw(Sy[0],Sy[1])
					
					for i in range(1, len(Sy)-1):
						for j in range(i+1, min(i+15, len(Sy)-1)):
							new_d = getDist_btw(Sy[i], Sy[j])
							
							if new_d < d_s:
								min_S , d_s = [Sy[i], Sy[j]] , new_d
					
					if d_s < delta:
						return min_S , d_s
					else:
						return min_points , delta
				
				else:
					return min_points , delta
		
			
		def minDistance(Points):
			
			PX = sorted(Points)
			PY = Points[:]
			PY.sort(key= lambda x:x[-1])
			
			close, min_d = closestpair(PX, PY)
			
			return min_d
		```

- ##### Integer Multiplication
	- Split the $n$ bits numbers into two groups of $n/2$![[Screenshot 2023-11-14 at 6.02.31 PM.png]]
	- rewrite $xy$ as $$(x_1 \cdot 2^{n/2} + x_0) (y_1 \cdot 2^{n/2} + y_0) $$
	- regroup as $$x_1y_1 \cdot 2^n + 2^{n/2}\cdot(x_1 y_0 + x_0 y_1) + x_0 y_0$$
	- ### Karatsuba's algorithm
		- complexity: $O(n^{\log 3}) \approx O(n^{1.59})$
		- First step: $(x_1 - x_0) (y_1 - y_0) = x_1y_1 - x_1y_0 - x_0y_1 + x_0y_0$
		- Compute: $x_1 y_1$ , $x_0y_0$
		- $(x_1 y_1 + x_0y_0) - (x_1 - x_0)(y_1 - y_0)$ leaves $x_1 y_0 + x_0 y_1$
		```Python
		def Fast_Multiply(x, y, n): # x and y which are two n-bit numbers
			
			if n == 1:
				return x * y
			
			else:
				m = n/2
				(x1, x0) = (x / (2**m), x % (2**m)) # bit shifting
				(y1, y0) = (y / (2**m), y % (2**m)) # bit shifting
				(a, b) = (x1 - x0, y1 - y0)
				
				p = Fast_Multiply(x1, y1, m)
				q = Fast_Multiply(x0, y0, m)
				r = Fast_Multiply(a, b, m)
			
			return p * (2**n) + (p+q-r) * (2**n/2) + q
		```

- ##### Recursion Trees
	- recursive tree: rooted tree with on node for each recursive subproblem
	- value of each node: time spent on the subproblem <u>excluding</u> recursive calls
	- for an input size of $n$:
		- $f(n)$: time spent on non-recursive work
		- $r$: number of recursive calls
		- $n/c$: each recursive call works on a subproblem of size $n/c$
		- Merge sort made $2$ recursive calls, so $r = 2$; and $c=2$ because we did it on size $n/2$
		- Binary search made $1$ recursive call, so $r = 1$; and $c=2$ because we did it on size $n/2$
		- Karatsuba's made made $3$ recursive call, so $r = 3$; and $c=2$ because we did it on size $n/2$
	- Each node at level $d$ has value $f(n/c^d)$![[Screenshot 2023-11-15 at 2.06.29 PM.png]]
	- Leaves correspond to the base case $T(1)$
	- Level $i$ has $r^i$ nodes, each with value $f(n/c^i)$
	- Tree has $L$ levels; where $L =  \log_c n$
	- Total cost $T(n) = \sum_{i=0}^L r^i \cdot f(n/c^i)$
	- number of leaves is $r^L$
		- Last term in the level by level sum is $n ^{\log_c r}$, i.e., the total cost at the leaf level
	- <u>Total cost</u>
		1. <u>Decreasing series</u>: each term is a constant factor smaller than previous term
			- example: binary search
			- root dominates the sum, $T(n)  = O(f(n))$
		2. <u>Equal</u>: all terms in the series are equal
			- sum of the costs at level $i+1$ is equal to the cost of the parent of that thing
			- $T(n) = O(f(n) \cdot L) = O(f(n) \log n)$
		3. <u>Increasing</u>: series growing exponentially, each term is a constant factor larger than previous term
			- example: naïve search, any algorithm with exponential complexity 
			- Leaves dominate the sum $T(n) = O(n^{\log_c r})$
	- Merge sort: sum of each level is the same therefore total cost $T(n) = O(n \log n)$
	- Quick sort: If I can knock-off a fixed fraction by choosing a good pivot (e.g., if the pivot is somehow chosen to be between the $1/3^{rd}$ and $2/3^{rd}$ position), then total cost $T(n) = O(n \log n)$. 

- ##### Quick select
	- Find the $k^{th}$ largest value in a sequence of length $n$
	- If we can find median in $O(n)$, quick sort becomes $O(n \log n)$
	- quick sort partitions the list into $lower$ and $upper$ based on the $pivot$.
	- Let $m = \text{len}(lower)$. 3 scenarios:
		1. $k \leq m \to$ answer lies in $lower$           `select(lower, k)`
		2. $k = m+1 \to$ answer is $pivot$             `return(pivot)`
		3. $k > m+1 \to$ answer lies in $upper$     `select(upper, k - m +1)`
	- When the pivot is an extreme value: quickselect code given below has total cost $T(n) = O(n^2)$
		```Python
		def quickselect(L, l, r, k): # k-th largest in L[l:r]
			if (k < 1) or (k > r-l):
				return None
			
			(pivot, lower, upper) = (L[l], l+1, l+1)
			for i in range(l+1, r):
				if L[i] > pivot: # extend upper segment
					upper += 1
				else: # Exchange L[i] with start of upper segment
					(L[i] , L[lower]) = (L[lower] , L[i])
					(lower , upper) = (lower + 1 , upper + 1)
				
			(L[l] , L[lower-1]) = (L[lower-1] , L[l]) # move pivot 
			lower -= 1
			
			# recursive calls
			lowerlen = lower - 1
			if k <= lowerlen:
				return quickselect(L, l, lower, k)
				
			elif k == lowerlen + 1:
				return L[lower]
				
			else:
				return quickselect(L, lower + 1, r, k - lowerlen + 1)
		```
	- <u>Median of medians</u>: to find a good pivot
		- Divide $L$ into blocks of $5$. Find the median of each block (brute force)
		- Let $M$ be the list of block medians. Recursively apply the process to $M$.
		- Fastselect given below has total cost $T(n) = O(n)$
		```Python
		def MoM(L): # Median of medians
			if len(L) <= 5:
				L.sort()
				return (L[len(L)//2])
			
			# construct list of block medians
			M = []
			for i in range(0, len(L), 5):
				X = L[i:i+5]
				X.sort()
				M.append(X[len(X)//2])
			
			return MoM(M)


		def fastselect(L, l, r, k): # k-th largest in L[l:r]
			if (k < 1) or (k > r-l):
				return None
			
			# Find MoM pivot and move to L[l]
			pivot = MoM(L[l:r])
			pivotpos = min([i for i in range(l,r) if L[i] == pivot])
			(L[l] , L[pivotpos]) = (L[pivotpos] , L[l])
			
			(pivot, lower, upper) = (L[1], l+1, l+1)
			for i in range(l+1, r):
				if L[i] > pivot: # extend upper segment
					upper += 1
				else: # Exchange L[i] with start of upper segment
					(L[i] , L[lower]) = (L[lower] , L[i])
					(lower , upper) = (lower + 1 , upper + 1)
				
			(L[l] , L[lower-1]) = (L[lower-1] , L[l]) # move pivot 
			lower -= 1
			
			# recursive calls
			lowerlen = lower - 1
			if k <= lowerlen:
				return fastselect(L, l, lower, k)
				
			elif k == lowerlen + 1:
				return L[lower]
				
			else:
				return fastselect(L, lower + 1, r, k - lowerlen + 1)
		```


# <u>Week 9</u>
- #### Intro
	- Interval scheduling
		- scheduling teacher with fixed time intervals into a classroom such that you maximise the number of teachers who get to use the room
		- Each subset of bookings is a subproblem
		- Generic <u>greedy strategy</u>: pick one request; eliminate bookings in conflict with the choice; solve the resulting problem
		- Given $N$ bookings, $2^N$ subproblems. Greedy strategy looks at only a small fraction of subproblems (each choice rules out a large number of subproblems)
	- Weighted Interval scheduling
		- same scenario as before but each request for booking comes with a weight
		- revised goal: maximise the total weight of the booking that are selected
		- Solution:
			1. Order the booking by starting time $\{b_1, b_2, \ldots, b_n \}$ in ascending order
			2. Begin with $b_1$.
				- If $b_1$ is part of optimal solution, eliminate conflicting requests and solve the resulting subproblem
				- If $b_1$ is <u>not</u> part of optimal, eliminate $b_1$ and solve $\{b_2, \ldots, b_n \}$
				- Evaluate whether the maximum of ( $b_1 + \text{subproblem}_1$ , $\text{subproblem}_2$ )
			- If a subproblem at some later stage is the same as a subproblem solved earlier, it is wasteful to recompute.

- ### Memoization
	- <big>Memory table</big>: Build a table of values already computed
	- Memoization: check if the value to be computed exists in the memory table
		- store each newly computed value in a table
		- look up the table before making a recursive call
		- computation tree becomes linear
	- "Top-down"
	- Implementation of fibonacci using memory table
		```Python
		def fib(n):
			if n in fibtable.keys():
				return fibtable[n]
			
			if n <= 1:
				value = n
			else:
				value = fib(n-1) + fib(n-2)
			
			fibtable[n] = value
			
			return value
		```

- ### Dynamic Programming
	- anticipate the structure of subproblems
		- derive from inductive definition
		- the <u>dependency structure</u> among the subproblems from a <u>Directed Acyclic Graph</u>
	- "Bottom-up"
	- Solve subproblems in topological order, starting with the base case, i.e. the subproblem with no dependencies
		- Never need to make a recursive call.

- #### Grid path
	- Every path from $(0,0)\ \text{to}\ (m,n)$ has $m+n$ steps
		- Out of $m+n$, $m$ as moves in x-axis and $n$ are moves in y-axis.
		- fixing the position of $m$ moves among the total $m+n$ moves gives total number of combinations:$$\text{number of possible paths} = \binom{m+n}{m} = \binom{m+n}{n}$$
		- example: $(0,0)\ \text{to}\ (5,10)$ has $3003$ possible paths $$\text{number of possible paths} = \binom{5+10}{5} = 3003$$
	- If you're <u>not allowed to go to some point</u> $(p,q)$ in any of the paths
		- subtract the number of paths crossing $(p,q)$ in their way from $(0,0)\ \text{to}\ (m,n)$ $$\text{number of paths crossing}\ (p,q) = \binom{p+q}{p} \times \binom{(m-p)+(q-n)}{(m-p)}$$
		- example: from $(0,0)\ \text{to}\ (m,n)$ but not allowed to cross $(2,4)$ $$\text{paths crossing}\ (2,4) = \binom{2+4}{2} \times \binom{3+6}{3} = 1260$$ $$\text{valid paths excluding}\ (2,4) = 3003 - 1260 = 1743$$
	- <u>inclusion-exclusion — counting is messy</u>. Example: what if there were multiple point that you weren't allowed to pass on the path?
	- #### Inductive formulation
		- number of paths from $(0,0)$ to $(i,j)$
			- $P(i,j) = P(i-1,j) + P(i,j-1)$
			- $P(0,0) = 1$                  — base case
			- $P(i,0) = P(i-1,0)$    — bottom row
			- $P(0,j) = P(0,j-1)$    — left column
			- $P(i,j) = 0$                   — if I am not allowed to cross $(i,j)$
		- ##### Dynamic Programming
			- Identify DAG structure. 
			- $P(0,0)$ has no dependencies
			- Start at $(0,0)$. Fill row by row, column by column or diagonal by diagonal![[Screenshot 2023-11-25 at 2.50.01 PM.png]]

- Dynamic Programming doesn't care whether a subproblem is going to be used or not. Memoization calculates only the subproblems that are recursively called.
	- but dynamic programming can be done iteratively as opposed to the recursive method of memoization, which makes dynamic programming more efficient in some cases due to lesser number of recursive calls.

- #### Common subwords
	- find the longest common subword in two strings.
		- "secret" & "secretary"     — "secret", length $6$
		- "bisect" & "secret"           — "sec", length $3$
		- "director" & "secretary"   — "ec", or "re", length $2$
	- Problem:
		- $u = a_0a_1 \ldots a_{m-1}$
		- $v = b_0b_1 \ldots b_{n-1}$
		- common subword of length $k$ — for some positions $i$ and $j$, i.e., $a_ia_{i+1} \ldots a_{i+k-1} = b_jb_{j+1} \ldots b_{j+k-1}$
		- $LCW(i,j)$ — length of the longest common subword starting at $i$ and $j$$$LCW(i,j) = \begin{cases} 1 + LCW(i+1,j+1) &\text{if}\ a_i = b_j \\ 0 &\text{if}\ a_i \neq b_j \\ 0 & \text{if}\ i=m\ \text{or}\ j=n\ \end{cases}$$
			- $\text{If}\ a_i \neq b_j,\ LCW(i,j)=0$
			- $\text{If}\ a_i = b_j,\ LCW(i,j)= 1+ LCW(i+1,j+1)$
			- $LCW(m,n) = 0$                  — base case, reached the end of the both strings
			- $LCW(i,n) = 0\ \forall 0\leq i \leq m$  — empty string on one side
			- $LCW(m,j) = 0\ \forall 0\leq j \leq n$  — empty string on one side
	- <u>Dynamic Programming</u>
		- Table of $(m+1) \cdot (n+1)$ values
		- $LCW(i,j)$ depends on $LCW(i+1,j+1)$
		- Start at bottom right and fill column by column (or row by row)![[Screenshot 2023-11-25 at 3.17.07 PM.png]]
		- Implementation; complexity: $O(mn)$
		```Python
		import numpy as np
		def LCW(u,v):
			(m,n) = (len(u), len(v))
			lcw_table = np.zeros((m+1, n+1))
			
			maxlcw = 0
			maxword = ''
			
			for j in range(n-1,-1,-1):
				for i in range(m-1,-1,-1):
					
					if u[i] == v[j]:
						lcw_table[i,j] = 1 + lcw_table[i+1,j+1]    
					else:
						lcw_table[i,j] = 0
						
					if lcw_table[i,j] > maxlcw:
						maxlcw = int(lcw_table[i,j])
						maxword = u[i:i+maxlcw]
						
			return maxlcw, maxword
		```

- #### Common sequence
	- subsequence — can drop some letters in between
		- "secret" & "secretary"     — "secret", length $6$
		- "bisect" & "secret"           — "sect", length $4$
		- "director" & "secretary"   — "ectr", or "retr", length $4$
	- Applications: Analysing genes, `diff` command in Unix/Linux
	- $LCS(i,j)$ — length of the longest common subsequence$$LCS(i,j) = \begin{cases} 1 + LCS(i+1,j+1) &\text{if}\ a_i = b_j \\ \max(LCS(i,j+1) , LCS(i+1,j)) &\text{if}\ a_i \neq b_j \\ 0 & \text{if}\ i=m\ \text{or}\ j=n\ \end{cases}$$![[Screenshot 2023-11-25 at 4.08.55 PM.png]]
	- Implementation
		```python
		import numpy as np
		def LCS(u,v):
		    (m,n) = (len(u), len(v))
		    lcs_table = np.zeros((m+1, n+1))
		    
		    for j in range(n-1,-1,-1):
		        for i in range(m-1,-1,-1):
		            
		            if u[i] == v[j]:
		                lcs_table[i,j] = 1 + lcs_table[i+1,j+1]    
		            else:
		                lcs_table[i,j] = max( lcs_table[i+1,j] , lcs_table[i,j+1] ) 
		                
		    return lcs_table[0,0]
		```

- #### Edit Distance
	- Edit operations: insert, delete, substitute
	- Minimum number of edit operations needed to go from one string to another.
	- Levenshtein distance
	- Application: suggestions for spelling correction; genetic similarity of species
	- longest common subsequence: minimum number of deletes needed to make them equal
		- deleting a letter from $u$ is equivalent to inserting it in $v$
		- $LCS$ is equivalent to edit distance without substitution
	- Problem:
		- $u = a_0a_1 \ldots a_{m-1}$
		- $v = b_0b_1 \ldots b_{n-1}$
		- aim is to transform $u$ to $v$
		- $ED(i,j)$ — edit distance $$ED(i,j) = \begin{cases} ED(i+1,j+1) & \text{if}\ a_i = b_j \\ 1 + \min(ED(i+1, j+1) , ED(i+1,j), ED(i,j+1) & \text{if}\ a_i \neq b_j \\ 0 & \text{if}\ i=m\ \text{and}\ j=n\ \\ m-i & \text{if}\ j = n \\ n-j & \text{if}\ i = m \end{cases}$$
		- If $a_i \neq b_j$  take minimum of
			- substitute $a_i$ by $b_j$    ,OR
			- delete $a_i$                   ,OR
			- insert $b_j$ before $a_i$
		- base cases: either both lists are exhausted, or one of the list is exhausted (insert/delete the remaining elements)
		- in the path, step down means delete, and step right means insert![[Screenshot 2023-11-25 at 7.09.37 PM.png]]
		- implementation
		```python
		import numpy as np
		def ED(u,v):
		    (m,n) = (len(u), len(v))
		    ed_table = np.zeros((m+1, n+1))
		    
		    for i in range(m-1,-1,-1):
		        ed_table[i,n] = m-i
		        
		    for j in range(n-1,-1,-1):
		        ed_table[m,j] = n-j
		        
		    for j in range(n-1,-1,-1):
		        for i in range(m-1,-1,-1):
		            
		            if u[i] == v[j]:
		                ed_table[i,j] = ed_table[i+1,j+1]
		            else:
		                ed_table[i,j] = 1 + min(ed_table[i+1,j+1],
		                                        ed_table[i,j+1],
		                                        ed_table[i+1,j])
		                
		    return ed_table[0,0]
		```

- #### Matrix Multiplication
	- multiply matrices $A \cdot B = C$ $$C[i,j] = \sum_{k=0}^{n-1} A[i,k] \cdot B[k,j] $$
	- If $A = m \times n\ \text{and}\ B = n \times p$, computing each entry in $C$ takes $O(n)$ time, and $C$ has $m \times p$ entries. Therefore, total complexity to compute $C = O(mnp)$
	- matrix mult is associative: $ABC = (AB)C = A(BC)$ but can affect the complexity![[Screenshot 2023-11-25 at 8.16.45 PM.png]]
	- Given $n$ matrices, $M_0:r_o \times c_0, \ldots, M_{n-1}:r_{n-1} \times c_{n-1}$, find the optimal order of multiplication
	- Solution:
		- Final step: $(M_0 \cdot M_1 \cdots M_{k-1}) \cdot (M_k \cdot M_{k+1} \cdots M_{n-1})$ for some $0<k<n$
		- first term dimension: $r_0 \times c_{k-1}$
		- second term dimension: $r_k \times c_{n-1}$ , where $r_k = c_{k-1}$
		- $C(0,n-1)$ denotes the total cost
		- cost of building first and second factor: $C(0,k-1)$ and $C(k,n-1)$
		- final step complexity: $O(r_o r_k c_{n-1})$
		- $C(0,n-1) = C(0,k-1) + C(k,n-1) + r_o r_k c_{n-1}$
		- Inductive structure:
			- $C(j,k) = \min_{j<l\leq k}[C(j,l-1) + C(l,k) + r_j r_l c_k]$
			- Base case: $C(j,j) = 0 \ ,\ \forall\ 0 \leq j < n$   when there is only one matrix
			- Blue shaded area is not possible.
			- $C(i,j)$ depends on $C(i,k-1), C(k,j)$ for every $i < k \leq j$ . Therefore every entry has $O(n)$ dependencies ![[Screenshot 2023-11-25 at 8.58.03 PM.png]]
			- Diagonal entires are base case. Therefore, you <u>need to go diagonal by diagonal</u>
		- Implementation; complexity: filling a table of $n^2$ entries, where each entry takes $O(n)$, total cost $=O(n^3)$
		```Python
		import numpy as np
		def matrix_mul_order(dim):
		    # dim: dimension matrix, entries are pairs (r_i, c_i)
		    
		    n = dim.shape[0]
		    C = np.zeros((n,n))
		    
		    for i in range(n):
		        C[i,i] = 0
		        
		    for diff in range(1,n):
		        for i in range(0,n-diff):
		            
		            j = i + diff
		            C[i,j] = C[i,i] + C[i+1,j] + dim[i][0] * dim[i+1][0] * dim[j][1]
		            
		            for k in range(i+1,j+1):
		                C[i,j] = min(C[i,j],
		                             C[i,k-1] + C[k,j],
		                             dim[i][0]*dim[k][0]*dim[j][1])
		                
		    return C[0,n-1]
		```

# <u>Week 10</u>
- ### String Matching
	- example: 'an' occurs in 'banana' at two positions
	- a text `t` of length `n` and a pattern `p` of length `m`
		- find every position `i` in `t` such that `t[i:i+m] == p`
	- Brute force; complexity: $O(nm)$
		```python
		def stringmatch_bruteforce(t,p):
			poslist = []
			for i in range(len(t) - len(p) + 1):
				matched = True
				j = 0
				
				while j < len(p) and matched:
					if t[i+j] != p[j]:
						matched = False
					j += 1
				
				if matched:
					poslist.append(i)
			return poslist
		
		def stringmatch_bruteforce_reverse(t,p):
			poslist = []
			for i in range(len(t) - len(p) + 1):
				matched = True
				j = len(p)-1
				
				while j >=0 and matched:
					if t[i+j] != p[j]:
						matched = False
					j -= 1
				
				if matched:
					poslist.append(i)
			return poslist
		```

- ### Boyer-Moore Algorithm
	- If the last <u>alphabet doesn't occur in the pattern</u>, while doing brute force string matching in reverse, skip searching for pattern if the last item ![[Screenshot 2023-11-29 at 6.24.53 PM.png]]While looking for `'bulk'` in `'bananamania'`, for example, the first iteration matched `'a'` with `'k'`. In this case, `'a'` doesn't occur in the pattern so we can skip the next three alphabets in `'bananamania'`
	- If an alphabet does occur in the pattern, alight rightmost occurrence of that alphabet in pattern with the alphabet in the text.![[Screenshot 2023-11-29 at 6.34.08 PM.png]]Use a dictionary `'last'`:
		- for each `c` in `p`, `last[c]` records right-most position of `c` in `p`
		- shift pattern by `j - last[c]`
		- `If c not in last.keys()` shift pattern by `j+1`
	- Implementation; complexity: $O(nm)$
	```Python
	def boyermoore(t,p):
		last = {}
		for i in range(len(p)):
			last[p[i]] = i
		
		postlist , i = [] , 0
		while i <= (len(t) - len(p)):
			matched , j = True , len(p)-1
			
			while j >= 0 and matched:
				if t[i+j] != p[j]:
					matched = False
				j -= 1
			
			if matched:
				poslist.append(i)
				i += 1
			else:
				j += 1
				if t[i+j] in last.keys():
					i += max(j - last[t[i+j]], 1)
				else:
					i += j + 1
		
		return poslist
	```

- ### Rabin-Karp Algorithm
	- numeric comparison
	- Suppose each alphabet can be thought of as a number in base 10 $=\{0,1,\ldots,9\}$
	- Convert a block `t[i:i+m]` into a number `num` in one scan
		```python
		num = 0
		for j in range(m):
			num = 10*num + int(t[i+j])
		```
	- Implementation
		```Python
		def rabinkarp(t,p):
			poslist = []
			
			numt , nump = 0,0
			for i in range(len(p)):
				numt = 10*numt + int(t[i])
				nump = 10*nump + int(p[i])
			
			if numt == nump:
				poslist.append(0)
			
			for i in range(1, len(t) - len(p)+1):
				numt = numt - int(t[i-1]) * (10 ** (len(p)-1))
				numt = 10*numt + int(t[i + len(p)-1])
				if numt == nump:
					poslist.append(i)
			
			return poslist
		```
	- each alphabet is assigned a number. $\Sigma = \{a_1,a_2,\ldots,a_k\}$ treat each letter as a digit in base $k$.
		- multiply/divide by $k$ rather than $10$
		- for realistic $k$, the numbers are too large to work with directly.
		- instead, do all computations modulo a suitable prime $q$

- #### Automata
	- re-use partial matches
		- keep track of longest <u>prefix</u> of `p[:k]` that we have matched. This prefix is a <u>suffix</u> of `t[:i+j]`
		- If `t[i+j] == p[k]`, extend the match. else, reset longest match for `t[:i+j+1]`
	- Precomputing longest match as a graph
		- Pattern `p` of length `m`
		- graph with `m+1` nodes, $\{0,1,\ldots,m\}$; node `i` denotes match upto `p[:i]`
		- `t[j] = a, t[:j]` matched `p[:i]`
			- Edge `i` $\to$ `k`, `t[:j+1]` matches `p[:k]`
				- If `t[j] == p[i]`, then `k = i + 1`
				- else: find longest prefix of `p` that matches suffix of `t[:j+1]`
			- with brute force, every edge takes $O(m^2)$. Overall $O(m^3)$
		- This graph is a.k.a. <u>finite state automaton</u>
			- nodes are states
			- edges are transitions
		- example: with `t= 'abababac'` and `p = 'ababac'`![[Screenshot 2023-11-29 at 9.32.15 PM.png]]Single scan suffices. no need to 're-scan' whenever we find a mismatch

- ### Knuth-Morris-Pratt Algorithm
	- goal: compute automaton efficiently
	- a text `t` of length `n` and a pattern `p` of length `m`
	- match `p` against itself
		- `match[j] = k` if suffix of `p[:j+1]` matches prefix `p[:k]`. `j` is between $0$ and $m-1$
	- suppose suffix of `p[:j+1]` matches prefix `p[:k]` ![[Screenshot 2023-12-04 at 7.13.48 PM.png]]
		- if `p[j+1] == p[k]`, extend the match
		- otherwise, find a shorter prefix that can be extended by `p[j+1]`
	- The `match` function is generally referred to as a 'failure function' (where to fall back if match fails)
	- Implementation; complexit: $O(m)$
		- `j` is next position in `t`. `k` is currently matches position in `p`. $O(m+n) = O(n)$ 
		```python
		def kmp_fail(p):
			m = len(p)
			fail = [0 for i in range(m)]
			
			j,k = 1,0
			while j < m:
				
				if p[j] == p[k]: # k+1 characters match
					fail[j] = k+1
					j , k = j+1 , k+1
				
				elif k > 0: # find shorter prefix
					k = fail[k-1]
				
				else: # no match found at j
					j += 1
			
			return fail
		
		def find_kmp(t,p):
			n,m = len(t) , len(p)
			if m == 0:
				return 0
			fail = kmp_fail(p) # preprocessing
			j = 0 # index into text
			k = 0 # index into text
			
			while j < n:
				if t[j] == p[k]: # matched p[0:k+1]
					if k == m-1: # match complete
						return (j-m+1)
					j,k = j+1 , k+1 # extend match
					
					elif k > 0:
						k = fail[k-1] # use smaller prefix
					
					else:
						j += 1
			return -1
		```

- ### Tries
	- special kind of tree.
	- every maximal path is a word. Add special end of word symbol '$'
	- a set of words with $s$ words and $n$ total symbols will have $s$ number of leaves and at most $n+1$ nodes plus '$' nodes ![[Screenshot 2023-12-04 at 9.36.23 PM.png]]
	- ##### Auxiliary information
		- trie as key-value map where words are keys and values are relevant information
		- Trie vs hash function: time to look up is proportional to the length of the key; no collision; tries take up more space ![[Screenshot 2023-12-04 at 9.44.45 PM.png]]
	- Implementation
		```Python
		class Trie:
			def __init__(self, S=[]):
				self.root = {}
				for s in S:
					self.add(s)
			
			def add(self,s):
				curr = self.root
				s += '$'
				for c in s:
					if c not in curr.keys():
						curr[c] = {}
					curr = curr[c]
			
			def query(self,s):
				curr = self.root
				for c in s:
					if c not in curr.keys():
						return False
					curr = curr[c]
				
				if '$' in curr.keys():
					return True
				else:
					return None
		```
	- #### Suffix Trie
		- expand $S$ to include all suffixes; assume $S = \{s\}$. $suffix(S) = \{w\ |\ \exists v, vw = s \}$
		- using this, we can check if $w$ is a substring of $s$; and how many times does $w$ occur as a substring in $s$; what is the longest repeated substring in $s$![[Screenshot 2023-12-04 at 9.56.33 PM.png]]
		- a suffix trie for a word of length $n$ could have nodes proportional to $n$ or $n^2$
		- Implementation
			```python
			class SuffixTrie:
				def __init__(self, s):
					self.root = {}
					s += '$'
					
					for i in range(len(s)):
						curr = self.root
						for c in s[i:]:
							if c not in curr.keys():
								curr[c] = {}
							curr = curr[c]
				
				def followPath(self,s):
					curr = self.root
					for c in s:
						if c not in curr.keys():
							return None
						curr = curr[c]
					return curr
				
				def hasSubstring(self,s):
					return self.followPath(s) is not None
				
				def hasSuffix(self,s):
					node = self.folowPath(s)
					return ( (node is not None) and ('$' in node.keys()) )
			```

- ### Regular Expressions
	- #### Describing patterns
		- finite alphabets $\Sigma = \{a,b,c,\ldots  \}$
		1. Each $a \in \Sigma$ is a pattern — matches $\{a\}$
		2. If $p$ is a pattern matching $S_p$ and $q$ is a pattern matching $S_q$ then $p + q$ matches $S_p \cup S_q$
			- <u>example</u>: 'Srivatsan' or 'Srivathsan' are two patterns. 'Srivatsan' + 'Srivathsan' will match either 'Srivatsan' or 'Srivathsan'.
		3. If $p$ is a pattern matching $S_p$ and $q$ is a pattern matching $S_q$ then $pq$ matches $S_p \cdot S_q = \{uv\ |\ u \in S_p , v \in S_q \}$
			- it will match the set of words which decompose into the first part being from $S_p$ and the second part being from $S_q$
			- <u>example</u>: 'sub' and 'tion' are two patterns. 'substitution' , 'subtraction' will match
		4. If $p$ is a pattern matching $S_p$ then $p^+$ matches any word $w$ that can be decomposed as $w_1 w_2 \ldots w_k$ where each $w_j \in S_p$
			- $p^+$ is 1 or more repetitions of $p$ ; $p^*$ is 0 or more repetitions
			- <u>example</u>: 'na' is the pattern. matches 'banana' but not 'pancreas'
	- ###### Shortcuts
		- Want to match $a$ followed by $b$
			- any symbol from $\Sigma$ can come in between
			- $\Sigma = \{a_1,a_2, \ldots, a_k \}$ ; $a_1 + a_2 + \cdots + a_k$ matches any symbol in $\Sigma$
			- Use $\Sigma$ as an abbreviation for this special pattern
			- pattern we want: $a \Sigma^+ b$
			- if no gap between $a$ and $b$, target pattern: $a \Sigma^* b$
		- Looking for 'Srivatsan' or 'Srivathsan'
			- Pattern: $(\Sigma^* \text{Srivatsan} \Sigma^*) + (\Sigma^* \text{Srivathsan} \Sigma^*)$
			- by convention, drop $\Sigma^*$ — $(\text{Srivatsan} + \text{Srivathsan})$ matches anywhere in the text
			- more compactly: $\text{Srivat}(\text{h} + \epsilon)\text{san}$
				- $\epsilon$ matches the empty string, with no characters
	- Anchoring patterns
		- To match the start of the string, write ^$p$
		- To match the end of the string, write $p$$
			- <u>example</u>: '^ba' and 'na$' both match 'banana'
		- ^$p$$ will match if entire word matches $p$
			- <u>example</u>: '^bana$' does not match 'banana', but '^ba(na)<sup>+</sup>\$' does
	- for every automaton, we can construct a pattern $p$ that matches exactly the words that the automaton accepts
	- for every pattern $p$, we can construct an automaton that accepts all words that match $p$
	- python provides a library for matching regular expressions

# <u>Week 11</u>
- ### Linear Programming
	- optimisations: <u>shortest</u> path, <u>minimum</u> cost spanning tree, etc; subject to some constraints
	- Linear programming: constraints and objective to be optimised are linear functions
		- Constraints: given as a linear function
		- Objective: also a linear function
		- subject to the constraints, <u>optimise</u> the objective function
	- Optimum value lie at a vertex (of the feasible region that we draw by inserting all the constraints)![[Screenshot 2023-12-08 at 8.33.08 PM.png]]
	- #### Simplex algorithm
		1. Start at any vertex, evaluate objective.
		2. If an adjacent vertex has a better value, move.
		3. If current vertex is better than all neighbours, stop.
		- can be exponential, but efficient in practice
		- Existence of solutions
			- Feasible region is convex (if you draw a line between any two points in the shape, the entire line should stay within the shape)
			- may be empty — constraints are unsatisfiable, no solutions
			- may be unbounded — no upper/lower limit on objective
	- #### Example
		- Sweet shop wants to maximise profit. They sell 3 items (their profits per box, and their daily demand):
			- Barfis: ₹100 ; 200 boxes
			- Halwa: ₹600 ; 300 boxes
			- Rasmalai: ₹1300 ; unlimited
		- Production capacity: 400 boxes a day
		- Milk supply: can produce either 600 boxes of halwa or 200 boxes rasmalai. Rasmalai needs 3 times more milk
		- <u>Objective</u>: Maximise $100b + 600h + 1300r$
		- <u>Constraints</u>:
			- $b \leq 200$
			- $h \leq 300$
			- $b+h+r \leq 400$
			- $h + 3r \leq 600$
			- $b,h,r \geq 0$
		- Feasible region: ![[Screenshot 2023-12-08 at 8.47.04 PM.png]]
		- Solution:
			- Consider these constraints:
				- (A) $\to h \leq 300$
				- (B) $\to b+h+r \leq 400$
				- (C) $\to h+3r \leq 600$
			- Combine as: $$100 \cdot (A) + 100 \cdot (B) + 400 \cdot (C) = 100b + 600h + 1300r \leq 310000$$
- #### Production Planning example (handwoven carpets)
	- ###### Problem:
		- 30 employees, each produce 20 carpets a month; each with salary of ₹20,000; so the labour cost is ₹1000 per carpet
		- Seasonal monthly demand: $d_1, d_2, \ldots, d_{12}$ from Jan to Dec
		- Overtime (to cope with varying demand): pay 80% extra; overtime limit is 30% per worker. This means one worker cannot make more than 26 carpets / month; and each carpet made in overtime costs ₹1800
		- Hiring and firing (expand workforce): hiring cost ₹3200 per worker; firing cost ₹4000 per worker
		- Make surplus and store (costs ₹80 per carpet)
	- ###### Target:
		- $w_i$ :  workers in month $i$ , and $w_0 = 30$
		- $x_i$ : carpets made in month $i$
		- $o_i$ : carpets made in overtime, month $i$
		- $h_i$ : workers hired at start of month $i$
		- $f_i$ : worked fired at start of month $i$
		- $s_i$ : surplus carpets after month $i$ , and $s_0 = 0$
		- $72$ variables, plus $w_0, s_0$
	- ###### Constraints
		- $w_i , x_i, o_i, h_i, f_i, s_i \geq 0$
		- Carpets made = regular + overtime
			- $x_i = 20w_i + o_i$
		- Number of workers match hiring/firing
			- $w_i = w_{i-1} + h_i - f_i$
		- Number of stored carpets connected earlier stock, production, demand
			- $s_i = s_{i-1} + x_i - d_i$
		- Overtime production at most $6$ carpets per worker
			- $o_i \leq 6w_i$
	- ###### Objective
		- Minimise the cost $$\sum_{i=1}^{12} (20000\cdot w_i) + (3200\cdot h_i) + (4000\cdot f_i) + (80\cdot s_i) + (1800\cdot o_i) $$
	- ###### Solution
		- Run simplex and find a solution
		- Optimum may have fractional values. Round off the solution to the nearest integer and recompute the cost
- #### Bandwidth Allocation example
	- ###### Problem
		- 3 users, $A,B,C$ to be connected to each other. $a,b,c$ are the nearest 'hubs'. ![[Screenshot 2023-12-08 at 10.47.33 PM.png]]
		- Links have capacity constraints (in Mbps)
		- Each connection $A$—$B$, $B$—$C$, $A$—$C$ should have at least $2$ Mbps of bandwidth
		- Direct and/or indirect allowed:
			- $A \to a \to b \to B$
			- $A \to a \to c \to b \to B$
		- Each connection earns revenue, per Mbps
			- $A$—$B$: ₹300 / Mbps
			- $B$—$C$: ₹200 / Mbps
			- $A$—$C$: ₹400 / Mbps
		- Allocate bandwidth to maximise revenue
	- ###### Linear Program
		- $x_{AB}$ — bandwidth via short connection ($A \to a \to b \to B$)
		- $y_{AB}$ — bandwidth via long connection ($A \to a \to c \to b \to B$)
		- Likewise, $x_{AC}$, $y_{AC}$, $x_{BC}$, $y_{BC}$
		- Any traffic to/from $B$ must flow via edge $b-B$:
			- $x_{AB} + y_{AB} + x_{BC} + y_{BC} \leq 10$
		- Likewise for $A$ and $C$
			- $x_{AB} + y_{AB} + x_{AC} + y_{AC} \leq 12$
			- $x_{AC} + y_{AC} + x_{BC} + y_{BC} \leq 8$
		- for internal links
			- $x_{AB} + y_{AC} + y_{BC} \leq 6$
			- $x_{BC} + y_{AC} + y_{AB} \leq 13$
			- $x_{AC} + y_{AB} + y_{BC} \leq 11$
		- Pairwise bandwidth at least 2 Mbps
			- $x_{AB} + y_{AB} \geq 2$
			- $x_{BC} + y_{BC} \geq 2$
			- $x_{AC} + y_{AC} \geq 2$
		- Maximise:$$300\cdot(x_{AB} + y_{AB})\ +\ 200\cdot(x_{BC} + y_{BC})\ +\ 400\cdot(x_{AC} + y_{AC}) $$

- ### Network Flows
	- ###### Problem
		- Oil Network
		- DAG with pipeline and their capacities![[Screenshot 2023-12-09 at 4.00.49 PM.png]]
		- Ship as much oil as possible from $s$ to $t$
		- No storage along the way
		- A flow of $7$ units is possible.![[Screenshot 2023-12-09 at 4.02.01 PM.png]]
	- ###### Constraints
		- Each edge $e$ has a capacity $c_e$
		- Flow: $f_e$ for each edge $e$
			- $f_e \leq c_e$
			- at each node (except $s$ and $t$) sum of incoming flow equals sum of outgoing flows
	- ###### Linear Program
		- Variable $f_e$ for each edge $e$: $f_{sa}, f_{bd}, f_{ce}, \ldots$
		- capacity constraints per edge: $f_{ba} \leq 10, \ldots$
		- conservation of flow at each internal node, example: $f_{ad}+f_{ab} = f_{dc} +f_{de}+f_{dt}$
		- Objective: maximise flow volume
			- Maximise: $f_{sa}+f_{sb}+f_{sc}$
	- ### Max flow-min cut theorem
		- Edges $\{ad, bd, sc \}$ disconnect $s$ and $t$: $(s,t)$-cut![[Screenshot 2023-12-09 at 4.27.51 PM.png]]
		- Flow from $s$ to $t$ must go through this cut. Max flow cannot exceed capacity of min cut
		- Use the residual graph from Ford-Fulkerson algorithm to find the min cut

- ### Ford-Fulkerson Algorithm
	- Start with 0 flow
	- choose a path from $s$ to $t$ that is not saturated and augment the flow as much as possible. 
	- Build residual graph. Repeat previous two steps till there is not feasible flow from $s$ to $t$![[Screenshot 2023-12-09 at 4.18.32 PM.png]]
	- Flow $20$, $s \to a \to b \to t$. Build residual graph                               ![[Screenshot 2023-12-09 at 4.20.55 PM.png]]
	- Add flow $10$, $s \to b \to  a \to t$. Build residual graph                               ![[Screenshot 2023-12-09 at 4.22.05 PM.png]]
	- Add the two flows for a total of $30$
	- Use BFS to find augmenting path with fewest edges (take the shortest path). Then the iterations will be bounded by $|V| \times |E|$, regardless of capacities

- #### Reductions
	- We want to solve problem $A$
	- We know how to solve problem $B$![[Screenshot 2023-12-09 at 5.44.28 PM.png]]
	- Convert input for $A$ into input for $B$ and interpret output of $B$ as output of $A$![[Screenshot 2023-12-09 at 5.45.52 PM.png]]
	- If $A$ is known to be intractable and $A$ reduces to $B$, then $B$ must also be intractable, otherwise efficient solution for $B$ will yield efficient solution for $A$
	- Useful to understand what can (and cannot) be modelled in terms of LP and flows

- ### Intractability
	- ##### Checking Algorithms
		- efficient algorithms: polynomial time algorithms
		- generating a solution is harder than checking a solution. For example: a student is given a number $N$ and tasked with finding two primes $p,q$ such that $p \cdot q = N$
		- checking algorithm $C$ for problem $P$
	- ##### Boolean Satisfiability
		- $\neg\ x_j$ — negation of $x_j$
		- $x_i \vee x_j$ — $x_i$ or $x_j$
		- $x_i \wedge x_j$ — $x_i$ and $x_j$
		- ###### Clause 
			- formula $C$ of the form: $(x_1 \vee \neg\ x_2 \vee \cdots \vee\ x_n)$
			- Disjunction of <u>literals</u> (variables, negated variables)
		- ###### Formula
			- conjunction of clauses: $C_1 \wedge\ C_2 \wedge \cdots \wedge\ C_k$
		-  Generating a solution — $n$ variables — $2^n$ possible assignments
	- $U$ is an independent set of size $K$ iff $V \setminus U$  is a vertex cover of size $N-K$
	- ##### P and NP
		- <u>class NP</u>: class of algorithms for which the checking algorithm can be done efficiently
		- If we convert an optimisation problem into a checking problem by providing a bound, we add only a $\log$ factor (Binary search through solution space)
		- ###### Non-deterministic Polynomial time
			- Guess a solution and check it
			- origins in computability theory
			- Non-deterministic Turing machines
		- <u>class P</u>: class of problems with regular polynomial time algorithms (worst-case complexity)
			- P is included in NP — generate a solution and check it
		- P $\neq$ NP because for some problems, it's easier to check than to generate
		- Boolean Satisfiability can be constructed as a graph connecting each variable with its negation and reducing to 'independent set' problem![[Screenshot 2023-12-09 at 8.03.37 PM.png]]
	- ### NP-Completeness
		- <u>Every problem in NP can be reduced to SAT (Boolean Satisfiability)</u>
		- SAT is said to be complete for NP
			- belongs to NP
			- every problem in NP reduces to it
		- 