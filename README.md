
# Graphs Library

## 

# **Edges Class Documentation**

The **`Edges`** class is designed to manage a collection of edges represented by the **`Edge`** struct. It provides methods to create and retrieve edge information. Below, you will find an explanation of the class's methods and how to use them, along with examples.

## **Table of Contents**

1. **[Edge Struct](https://chat.openai.com/?model=text-davinci-002-render-sha#edge-struct)**
2. **[Edges Class](https://chat.openai.com/?model=text-davinci-002-render-sha#edges-class)**
    - **[Constructor](https://chat.openai.com/?model=text-davinci-002-render-sha#constructor)**
    - **[createEdges Method](https://chat.openai.com/?model=text-davinci-002-render-sha#createedges-method)**
    - **[getEdges Method](https://chat.openai.com/?model=text-davinci-002-render-sha#getedges-method)**

---

## **Edge Struct**

The **`Edge`** struct represents an edge between two nodes with an associated weight.

```cpp
cppCopy code
struct Edge {
    int nodeOne;
    int nodeTwo;
    int weight;
};

```

- **`nodeOne`**: An integer representing one endpoint of the edge.
- **`nodeTwo`**: An integer representing the other endpoint of the edge.
- **`weight`**: An integer representing the weight of the edge.

---

## **Edges Class**

The **`Edges`** class manages a collection of edges using the **`Edge`** struct.

### **Constructor**

```cpp
cppCopy code
Edges(int len);

```

- Initializes an instance of the **`Edges`** class.
- **`len`**: The number of edges to be managed by the instance.

**Example:**

```cpp
cppCopy code
Edges edges(3); // Creates an instance to manage 3 edges

```

### **createEdges Method**

```cpp
cppCopy code
private: void createEdges();

```

- This private method prompts the user to input values for each edge in the collection.

**Example:**

```cpp
cppCopy code
edges.createEdges(); // Prompts the user to input edge information

```

### **getEdges Method**

```cpp
cppCopy code
public: int** getEdges();

```

- Copies the edge information from the internal collection to a new 2D array and returns it.

**Example:**

```cpp
cppCopy code
int** edgeArray = edges.getEdges(); // Retrieves a copy of the edge information

```

---

## **Example Usage**

```cpp
cppCopy code
#include <iostream>int main() {
    Edges edges(3);

    // Populate edge information
    edges.createEdges();

    // Retrieve copied edge information
    int** edgeArray = edges.getEdges();

    // Display copied edge information
    for (int i = 0; i < 3; i++) {
        std::cout << "Edge " << i + 1 << ": ";
        std::cout << "Node " << edgeArray[i][0] << " - Node " << edgeArray[i][1];
        std::cout << " (Weight: " << edgeArray[i][2] << ")\n";
    }

    // Clean up allocated memory
    for (int i = 0; i < 3; i++) {
        delete[] edgeArray[i];
    }
    delete[] edgeArray;

    return 0;
}

```

---

# **AdjacencyList Class Documentation**

The **`AdjacencyList`** class manages an adjacency list representation of a graph. It provides methods to create and manipulate the adjacency list, as well as retrieve information from it. Below, you will find an explanation of the class's methods and how to use them, along with examples.

## **Table of Contents**

1. **[AdjListNode Struct](https://chat.openai.com/?model=text-davinci-002-render-sha#adjlistnode-struct)**
2. **[LinkedList Struct](https://chat.openai.com/?model=text-davinci-002-render-sha#linkedlist-struct)**
3. **[AdjacencyList Class](https://chat.openai.com/?model=text-davinci-002-render-sha#adjacencylist-class)**
    - **[Constructor](https://chat.openai.com/?model=text-davinci-002-render-sha#constructor)**
    - **[createAdjListNode Method](https://chat.openai.com/?model=text-davinci-002-render-sha#createadjlistnode-method)**
    - **[addNode Method](https://chat.openai.com/?model=text-davinci-002-render-sha#addnode-method)**
    - **[fillAdjListByUserInput Method](https://chat.openai.com/?model=text-davinci-002-render-sha#filladjlistbyuserinput-method)**
    - **[getAdjList Method](https://chat.openai.com/?model=text-davinci-002-render-sha#getadjlist-method)**
    - **[printAdjList Method](https://chat.openai.com/?model=text-davinci-002-render-sha#printadjlist-method)**

---

## **AdjListNode Struct**

The **`AdjListNode`** struct represents a node in the adjacency list.

```cpp
cppCopy code
struct AdjListNode {
    int data;
    int weight;
    AdjListNode* next;
};

```

- **`data`**: An integer representing the data stored in the node.
- **`weight`**: An integer representing the weight associated with the edge.
- **`next`**: A pointer to the next node in the linked list.

---

## **LinkedList Struct**

The **`LinkedList`** struct represents a linked list of adjacency list nodes.

```cpp
cppCopy code
struct LinkedList {
    AdjListNode* head;
};

```

- **`head`**: A pointer to the first node in the linked list.

---

## **AdjacencyList Class**

The **`AdjacencyList`** class manages an array of linked lists representing the adjacency list.

### **Constructor**

```cpp
cppCopy code
AdjacencyList(int numNodes);

```

- Initializes an instance of the **`AdjacencyList`** class.
- **`numNodes`**: The number of nodes in the graph.

**Example:**

```cpp
cppCopy code
AdjacencyList adjacencyList(5); // Creates an adjacency list for a graph with 5 nodes

```

### **createAdjListNode Method**

```cpp
cppCopy code
AdjListNode* createAdjListNode(int data, int weight);

```

- Creates a new adjacency list node with the given data and weight.
- Returns a pointer to the newly created node.

**Example:**

```cpp
cppCopy code
AdjListNode* newNode = adjacencyList.createAdjListNode(2, 8); // Creates a node with data 2 and weight 8

```

### **addNode Method**

```cpp
cppCopy code
void addNode(int index, int dest, int weight);

```

- Adds a new node with the given destination and weight to the linked list at the specified index in the array.

**Example:**

```cpp
cppCopy code
adjacencyList.addNode(0, 2, 5); // Adds a node with destination 2 and weight 5 to the linked list of node 0

```

### **fillAdjListByUserInput Method**

```cpp
cppCopy code
void fillAdjListByUserInput(char typeOfGraph);

```

- Fills the adjacency list with user-provided input.
- **`typeOfGraph`**: 'w' for weighted graph, 'g' for unweighted graph.

**Example:**

```cpp
cppCopy code
adjacencyList.fillAdjListByUserInput('w'); // Fills the adjacency list for a weighted graph based on user input

```

### **getAdjList Method**

```cpp
cppCopy code
LinkedList** getAdjList();

```

- Returns a pointer to the array of linked lists representing the adjacency list.

**Example:**

```cpp
cppCopy code
LinkedList** adjListArray = adjacencyList.getAdjList(); // Retrieves the adjacency list array

```

### **printAdjList Method**

```cpp
cppCopy code
void printAdjList();

```

- Prints the adjacency list along with node data and weights.

**Example:**

```cpp
cppCopy code
adjacencyList.printAdjList(); // Prints the adjacency list with node data and weights

```

---

## **Example Usage**

```cpp
cppCopy code
#include <iostream>int main() {
    AdjacencyList adjacencyList(4);

    // Fill the adjacency list with user input for a weighted graph
    adjacencyList.fillAdjListByUserInput('w');

    // Print the filled adjacency list
    adjacencyList.printAdjList();

    return 0;
}

```

# **Heap Class Documentation**

The **`Heap`** class implements a min-heap data structure for storing and managing a collection of edges. It provides methods to insert and extract edges while maintaining the heap property. Below, you will find an explanation of the class's methods and how to use them, along with examples.

## **Table of Contents**

1. **[Edge Struct](https://chat.openai.com/?model=text-davinci-002-render-sha#edge-struct)**
2. **[Heap Class](https://chat.openai.com/?model=text-davinci-002-render-sha#heap-class)**
    - **[Constructor](https://chat.openai.com/?model=text-davinci-002-render-sha#constructor)**
    - **[createEdge Method](https://chat.openai.com/?model=text-davinci-002-render-sha#createedge-method)**
    - **[swapEdges Method](https://chat.openai.com/?model=text-davinci-002-render-sha#swapedges-method)**
    - **[heapify Method](https://chat.openai.com/?model=text-davinci-002-render-sha#heapify-method)**
    - **[insertToHeap Method](https://chat.openai.com/?model=text-davinci-002-render-sha#inserttoheap-method)**
    - **[extractMinEdge Method](https://chat.openai.com/?model=text-davinci-002-render-sha#extractminedge-method)**
    - **[printHeap Method](https://chat.openai.com/?model=text-davinci-002-render-sha#printheap-method)**

---

## **Edge Struct**

The **`Edge`** struct represents an edge between two nodes with an associated weight.

```cpp
cppCopy code
struct Edge {
    int nodeOne;
    int nodeTwo;
    int weight;
};

```

- **`nodeOne`**: An integer representing one endpoint of the edge.
- **`nodeTwo`**: An integer representing the other endpoint of the edge.
- **`weight`**: An integer representing the weight of the edge.

## **Heap Class**

The **`Heap`** class manages a min-heap of edges.

### **Constructor**

```cpp
cppCopy code
Heap(int capacity);

```

- Initializes an instance of the **`Heap`** class with the specified capacity.
- **`capacity`**: The maximum number of edges the heap can store.

**Example:**

```cpp
cppCopy code
Heap minHeap(10); // Creates a min-heap with a capacity of 10

```

### **createEdge Method**

```cpp
cppCopy code
Edge createEdge(int src, int dest, int weight);

```

- Creates and returns an **`Edge`** instance with the given source, destination, and weight.

**Example:**

```cpp
cppCopy code
Edge newEdge = minHeap.createEdge(0, 1, 5); // Creates a new edge with source 0, destination 1, and weight 5

```

### **swapEdges Method**

```cpp
cppCopy code
void swapEdges(Edge* edgeOne, Edge* edgeTwo);

```

- Swaps the positions of two **`Edge`** instances within the heap.

**Example:**

```cpp
cppCopy code
Edge edge1, edge2; // Assume edge1 and edge2 are properly initialized
minHeap.swapEdges(&edge1, &edge2); // Swaps the positions of edge1 and edge2 in the heap

```

### **heapify Method**

```cpp
cppCopy code
void heapify(int index);

```

- Restores the heap property starting from a specified index within the heap.

**Example:**

```cpp
cppCopy code
int startIndex = 0;
minHeap.heapify(startIndex); // Restores the heap property starting from index 0

```

### **insertToHeap Method**

```cpp
cppCopy code
void insertToHeap(Edge newEdge);

```

- Inserts a new **`Edge`** instance into the heap while maintaining the heap property.

**Example:**

```cpp
cppCopy code
Edge newEdge; // Assume newEdge is properly initialized
minHeap.insertToHeap(newEdge); // Inserts the new edge into the heap

```

### **extractMinEdge Method**

```cpp
cppCopy code
Edge extractMinEdge();

```

- Extracts the minimum-weight **`Edge`** from the heap while maintaining the heap property.

**Example:**

```cpp
cppCopy code
Edge minEdge = minHeap.extractMinEdge(); // Extracts the minimum-weight edge from the heap

```

### **printHeap Method**

```cpp
cppCopy code
void printHeap();

```

- Prints the content of the heap, showing each edge's source, destination, and weight.

**Example:**

```cpp
cppCopy code
minHeap.printHeap(); // Prints the contents of the heap

```

---

## **Example Usage**

```cpp
cppCopy code
#include <iostream>int main() {
    Heap minHeap(10);

    // Create and insert edges
    Edge edge1 = minHeap.createEdge(0, 1, 5);
    minHeap.insertToHeap(edge1);

    Edge edge2 = minHeap.createEdge(1, 2, 3);
    minHeap.insertToHeap(edge2);

    Edge edge3 = minHeap.createEdge(2, 3, 7);
    minHeap.insertToHeap(edge3);

    // Print the heap
    minHeap.printHeap();

    // Extract and print the minimum edge
    Edge minEdge = minHeap.extractMinEdge();
    std::cout << "Extracted Minimum Edge: " << minEdge.nodeOne << " - " << minEdge.nodeTwo << " (Weight: " << minEdge.weight << ")\n";

    // Print the heap after extraction
    minHeap.printHeap();

    return 0;
}

```

## 

# **Graph Class Documentation**

The **`Graph`** class represents a graph and provides methods to work with its adjacency information using an adjacency matrix. Below, you will find an explanation of the class's methods and how to use them, along with examples.

## **Table of Contents**

1. **[Graph Class](https://chat.openai.com/?model=text-davinci-002-render-sha#graph-class)**
    - **[Constructor](https://chat.openai.com/?model=text-davinci-002-render-sha#constructor)**
    - **[edgesArrayToMatrix Method](https://chat.openai.com/?model=text-davinci-002-render-sha#edgesarraytomatrix-method)**
    - **[adjListToMatrix Method](https://chat.openai.com/?model=text-davinci-002-render-sha#adjlisttomatrix-method)**
    - **[Breadth-First Search (BFS)](https://chat.openai.com/?model=text-davinci-002-render-sha#breadth-first-search-bfs)**
    - **[Depth-First Search (DFS)](https://chat.openai.com/?model=text-davinci-002-render-sha#depth-first-search-dfs)**
    - **[traverseGraph Method](https://chat.openai.com/?model=text-davinci-002-render-sha#traversegraph-method)**
    - **[isConnected Method](https://chat.openai.com/?model=text-davinci-002-render-sha#isconnected-method)**
    - **[printMatrix Method](https://chat.openai.com/?model=text-davinci-002-render-sha#printmatrix-method)**

---

```cpp

```

```cpp

```

## **Graph Class**

The **`Graph`** class manages a graph's adjacency matrix representation and provides methods for graph traversal and analysis.

### **Constructor**

```cpp
cppCopy code
Graph(int numberNodes);

```

- Initializes an instance of the **`Graph`** class with a specified number of nodes.
- **`numberNodes`**: The total number of nodes in the graph.

**Example:**

```cpp
cppCopy code
Graph graph(5); // Creates a graph with 5 nodes

```

### **edgesArrayToMatrix Method**

```cpp
cppCopy code
void edgesArrayToMatrix(int** edges, int edgesLen);

```

- Converts an array of edges to an adjacency matrix representation.
- **`edges`**: A 2D array of edges.
- **`edgesLen`**: The length of the edges array.

**Example:**

```cpp
cppCopy code
int** edgesArray; // Assume edgesArray is properly initialized
int edgesLen = 5;
graph.edgesArrayToMatrix(edgesArray, edgesLen); // Converts the edges array to an adjacency matrix

```

### **adjListToMatrix Method**

```cpp
cppCopy code
void adjListToMatrix(LinkedList** linkedListArray);

```

- Converts an adjacency list representation to an adjacency matrix representation.
- **`linkedListArray`**: An array of linked lists representing the adjacency list.

**Example:**

```cpp
cppCopy code
LinkedList** adjListArray; // Assume adjListArray is properly initialized
graph.adjListToMatrix(adjListArray); // Converts the adjacency list to an adjacency matrix

```

### **Breadth-First Search (BFS)**

```cpp
cppCopy code
void bfs(int source);

```

- Performs a Breadth-First Search starting from a specified source node.
- **`source`**: The starting node for BFS.

**Example:**

```cpp
cppCopy code
int startNode = 0;
graph.bfs(startNode); // Performs BFS starting from node 0

```

### **Depth-First Search (DFS)**

```cpp
cppCopy code
void dfs(int source);

```

- Performs a Depth-First Search starting from a specified source node.
- **`source`**: The starting node for DFS.

**Example:**

```cpp
cppCopy code
int startNode = 0;
graph.dfs(startNode); // Performs DFS starting from node 0

```

### **traverseGraph Method**

```cpp
cppCopy code
void traverseGraph(int source);

```

- Traverses the entire graph using Depth-First Search.
- **`source`**: The starting node for DFS traversal.

**Example:**

```cpp
cppCopy code
int startNode = 0;
graph.traverseGraph(startNode); // Traverses the entire graph using DFS

```

### **isConnected Method**

```cpp
cppCopy code
bool isConnected();

```

- Checks if the graph is connected.
- Returns **`true`** if the graph is connected, otherwise **`false`**.

**Example:**

```cpp
cppCopy code
bool connected = graph.isConnected(); // Checks if the graph is connected

```

### **printMatrix Method**

```cpp
cppCopy code
void printMatrix();

```

- Prints the adjacency matrix representation of the graph.

**Example:**

```cpp
cppCopy code
graph.printMatrix(); // Prints the adjacency matrix

```

---

## **Example Usage**

```cpp
cppCopy code
#include <iostream>int main() {
    Graph graph(4);

    // Example: Convert edges to matrix
    int** edgesArray; // Assume edgesArray is properly initialized
    int edgesLen = 5;
    graph.edgesArrayToMatrix(edgesArray, edgesLen);

    // Example: Convert adjacency list to matrix
    LinkedList** adjListArray; // Assume adjListArray is properly initialized
    graph.adjListToMatrix(adjListArray);

    // Example: Perform BFS and DFS
    int startNode = 0;
    graph.bfs(startNode);
    graph.dfs(startNode);

    // Example: Traverse the entire graph
    graph.traverseGraph(startNode);

    // Example: Check if the graph is connected
    bool connected = graph.isConnected();

    // Example: Print the adjacency matrix
    graph.printMatrix();

    return 0;
}

```

## 

# **Weighted Class Documentation**

The **`Weighted`** class inherits from the **`Graph`** class and adds functionality for working with weighted graphs. It provides methods to perform Dijkstra's algorithm for finding shortest paths in weighted graphs. Below, you will find an explanation of the class's methods and how to use them, along with examples.

## **Table of Contents**

1. **[Weighted Class](https://chat.openai.com/?model=text-davinci-002-render-sha#weighted-class)**
    - **[Constructor](https://chat.openai.com/?model=text-davinci-002-render-sha#constructor)**
    - **[createMatrix Method](https://chat.openai.com/?model=text-davinci-002-render-sha#creatematrix-method)**
    - **[adjListToMatrix Method](https://chat.openai.com/?model=text-davinci-002-render-sha#adjlisttomatrix-method)**
    - **[minDistance Method](https://chat.openai.com/?model=text-davinci-002-render-sha#mindistance-method)**
    - **[dijkstra Method](https://chat.openai.com/?model=text-davinci-002-render-sha#dijkstra-method)**
    - **[dijkstraEfficient Method](https://chat.openai.com/?model=text-davinci-002-render-sha#dijkstraefficient-method)**
    - **[printDijkstra Method](https://chat.openai.com/?model=text-davinci-002-render-sha#printdijkstra-method)**

---

## **Weighted Class**

The **`Weighted`** class extends the **`Graph`** class to work with weighted graphs.

### **Constructor**

```cpp
cppCopy code
Weighted(int numberNodes);

```

- Initializes an instance of the **`Weighted`** class with a specified number of nodes.
- **`numberNodes`**: The total number of nodes in the graph.

**Example:**

```cpp
cppCopy code
Weighted weightedGraph(5); // Creates a weighted graph with 5 nodes

```

### **createMatrix Method**

```cpp
cppCopy code
void createMatrix();

```

- Fills the adjacency matrix with weights by taking user input.

**Example:**

```cpp
cppCopy code
weightedGraph.createMatrix(); // Fills the adjacency matrix with weights based on user input

```

### **adjListToMatrix Method**

```cpp
cppCopy code
void adjListToMatrix(LinkedList** linkedListArray);

```

- Converts an adjacency list representation to an adjacency matrix representation for a weighted graph.
- **`linkedListArray`**: An array of linked lists representing the adjacency list.

**Example:**

```cpp
cppCopy code
LinkedList** adjListArray; // Assume adjListArray is properly initialized
weightedGraph.adjListToMatrix(adjListArray); // Converts the adjacency list to an adjacency matrix

```

### **minDistance Method**

```cpp
cppCopy code
int minDistance(int* dist, bool* visited);

```

- Finds the index of the node with the minimum distance value from a source node.
- **`dist`**: An array containing the distances from the source node to all nodes.
- **`visited`**: An array indicating whether each node has been visited.

**Example:**

```cpp
cppCopy code
int* distances; // Assume distances array is properly initialized
bool* visited; // Assume visited array is properly initialized
int minIndex = weightedGraph.minDistance(distances, visited); // Finds the index of the node with the minimum distance

```

### **dijkstra Method**

```cpp
cppCopy code
int* dijkstra(int source);

```

- Performs Dijkstra's algorithm to find the shortest paths from a source node to all other nodes.
- **`source`**: The source node for the shortest path calculations.
- Returns an array containing the shortest distances from the source node to all nodes.

**Example:**

```cpp
cppCopy code
int sourceNode = 0;
int* shortestDistances = weightedGraph.dijkstra(sourceNode); // Performs Dijkstra's algorithm

```

### **dijkstraEfficient Method**

```cpp
cppCopy code
int* dijkstraEfficient(LinkedList** linkedListArray, int source);

```

- Performs an efficient version of Dijkstra's algorithm using a min-heap to find shortest paths.
- **`linkedListArray`**: An array of linked lists representing the adjacency list.
- **`source`**: The source node for the shortest path calculations.
- Returns an array containing the shortest distances from the source node to all nodes.

**Example:**

```cpp
cppCopy code
LinkedList** adjListArray; // Assume adjListArray is properly initialized
int sourceNode = 0;
int* shortestDistances = weightedGraph.dijkstraEfficient(adjListArray, sourceNode); // Performs efficient Dijkstra's algorithm

```

### **printDijkstra Method**

```cpp
cppCopy code
void printDijkstra(int* dist, int source);

```

- Prints the minimum distances calculated using Dijkstra's algorithm for each node from a specified source node.
- **`dist`**: An array containing the minimum distances.
- **`source`**: The source node used in the Dijkstra's algorithm.

**Example:**

```cpp
cppCopy code
int* shortestDistances; // Assume shortestDistances array is properly initialized
int sourceNode = 0;
weightedGraph.printDijkstra(shortestDistances, sourceNode); // Prints the minimum distances

```

---

## **Example Usage**
```cpp
cppCopy code
int* shortestDistances; // Assume shortestDistances array is properly initialized
int sourceNode = 0;
weightedGraph.printDijkstra(shortestDistances, sourceNode); // Prints the minimum distances

```
