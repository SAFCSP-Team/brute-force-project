# Brute Force Project


### Objective

In this project, our objective is to understand how to use brute force algorithm.


### Problem


Implement `bruteforcePaths` method to find all possible paths in a graph.

### Implementation

* Create `bruteForcePaths` method that takes a `Graph` object and `startVertex` as parameters.
   *  initializes an array called `path` to store the current path and a boolean array called `visited`.
   *  calls the `generatePaths` method.
* In the `generatePaths` method:
     *  marks the `vertices` as visited by setting `visited[vertices]` to true.
     *  adds the `vertices` to the `path` array at the current `pathIndex`
     *   **increments** `pathIndex`.

the output
  ```
0 1 2 3 
0 2 2 2 
0 2 2 3 
0 2 3 3 
0 3 3 3 
 ```

```java

import java.util.ArrayList;
import java.util.List;

public class BruteForceGraph {

    static class Edge {
        int source;
        int destination;

        public Edge(int source, int destination) {
            this.source = source;
            this.destination = destination;
        }
    }

    static class Graph {
        int vertices;
        List<Edge> edges;

        public Graph(int vertices) {
            this.vertices = vertices;
            edges = new ArrayList<>();
        }

        public void addEdge(int source, int destination) {
            Edge edge = new Edge(source, destination);
            edges.add(edge);
        }
    }

    public static void bruteForcePaths() {
       boolean[] visited = new boolean[graph.vertices];

        /* write your code here */
    }


   public static void generatePaths(Graph graph, int vertices, boolean[] visited, int[] path, int pathIndex) {

     /* write your code here */

  if (pathIndex == graph.vertices) {
        printPath(path);
    } else {
        for (Edge edge : graph.edges) {
            if ((edge.source == vertices &&!visited[edge.destination]) ||
                    (edge.destination == vertices &&!visited[edge.source])) {
                generatePaths(graph, edge.destination, visited, path, pathIndex);
            }
        }
    }
}

    public static void printPath(int[] path) {
        for (int vertex : path) {
            System.out.print(vertex + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int numVertices = 4;
        Graph graph = new Graph(numVertices);

        graph.addEdge(0, 1);
        graph.addEdge(0, 2);
        graph.addEdge(0, 3);
        graph.addEdge(1, 2);
        graph.addEdge(2, 3);

        int startVertex = 0;
        bruteForcePaths(graph, startVertex);
    }
}


```
