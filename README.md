# Brute Force Project


## Objective

In this project, our objective is to understand how to use brute force algorithm.


## Problem


Create `bruteForcePaths` to find all possible paths in a graph.

## Implementation

* Create `bruteForcePaths` method that takes a `Graph` object and `startVertex` as parameters.
* initializes an array called `path` to store the current path and a boolean array called `visited` to track which vertices have been visited and then calls the `generatePaths` method.
* Create `generatePaths` method it takes the `Graph` object, the `currentVertex`, the `path` array, the `visited` array, and the `pathIndex` in the path array as parameters.
* marks the `currentVertex` as visited by setting `visited[currentVertex]` to true.
* adds the `currentVertex` to the `path` array at the current `pathIndex` and **increments** `pathIndex`.
* If the `pathIndex` is equal to `graph.vertices`, In that case, it calls the `printPath` method to print the `path`.
* If the `pathIndex` is not equal to `graph.vertices` iterates over the edges in the graph and checks if there is an edge starting from the current vertex `edge.source == currentVertex` and if the destination vertex of the edge has not been visited `!visited[edge.destination]`. If these conditions are met, it recursively 
 calls `generatePaths` with the destination vertex as the new current vertex, and it continues exploring the graph.
* and marks the current vertex as unvisited `visited[currentVertex] = false` to allow  it to be visited again in other paths.

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
        /* Write your code here */
    }

   public static void generatePaths() {
     /* Write your code here */
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
