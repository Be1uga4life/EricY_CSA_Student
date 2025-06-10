---
title: Graph Heuristics - Data Structures
comments: True
layout: post
description: Explanations of searches
author: Srijan, Matthew, Trevor
type: ccc
nav: nav/graph-heuristics.html
permalink: /heuristics/searches
courses: {'csa': {'week': 32}}
---

## **Traditional vs. Heuristic Approaches**


### **Dijkstra's Algorithm (Traditional)**

Dijkstra's algorithm is a **systematic, exhaustive search** that:b 



* Explores all possible paths in order of increasing cost
* **Guarantees the optimal solution**
* **Does NOT use estimation** - it calculates exact distances
* Time complexity: O((V + E) log V) where V = vertices, E = edges

```java
// Dijkstra's Algorithm - No Heuristic Used

public class DijkstraExample {

    public static void dijkstra(int[][] graph, int source) {

        int vertices = graph.length;

        int[] distances = new int[vertices];

        boolean[] visited = new boolean[vertices];

        

        // Initialize distances to infinity

        Arrays.fill(distances, Integer.MAX_VALUE);

        distances[source] = 0;

        

        for (int i = 0; i &lt; vertices - 1; i++) {

            int minVertex = findMinDistance(distances, visited);

            visited[minVertex] = true;

            

            // Update distances to neighbors

            for (int v = 0; v &lt; vertices; v++) {

                if (!visited[v] && graph[minVertex][v] != 0) {

                    int newDistance = distances[minVertex] + graph[minVertex][v];

                    if (newDistance &lt; distances[v]) {

                        distances[v] = newDistance;

                    }

                }

            }

        }

    }

}
```

### **The Problem with Traditional Methods**

For large graphs (like road networks with millions of intersections), Dijkstra's algorithm becomes impractical because it must explore too many possibilities.

## **Common Graph Heuristics**


### **1. Greedy Best-First Search**

Greedy Best-First Search makes decisions based **solely on the heuristic estimate** to the goal, ignoring the actual cost traveled so far.


#### **Mathematical Foundation**



* **Heuristic Function h(n)**: Estimates cost from node n to goal
* **Selection Criteria**: Always choose the node with the smallest h(n) value
* **Trade-off**: Speed vs. optimality (may not find the best path)


#### **Example: Manhattan Distance Heuristic**

For grid-based pathfinding, the Manhattan distance serves as an excellent heuristic:

h(current) = |current.x - goal.x| + |current.y - goal.y|

#### **Implementation Example**
```java

public class GreedyBestFirst {

    static class Node implements Comparable&lt;Node> {

        int x, y;

        int heuristic; // h(n) - estimated cost to goal

        

        public Node(int x, int y, int goalX, int goalY) {

            this.x = x;

            this.y = y;

            this.heuristic = Math.abs(x - goalX) + Math.abs(y - goalY);

        }

        

        @Override

        public int compareTo(Node other) {

            return Integer.compare(this.heuristic, other.heuristic);

        }

    }

    

    public static List&lt;Node> greedySearch(int[][] grid, 

                                         int startX, int startY, 

                                         int goalX, int goalY) {

        PriorityQueue&lt;Node> openSet = new PriorityQueue&lt;>();

        Set&lt;String> visited = new HashSet&lt;>();

        Map&lt;String, Node> cameFrom = new HashMap&lt;>();

        

        Node start = new Node(startX, startY, goalX, goalY);

        openSet.add(start);

        

        while (!openSet.isEmpty()) {

            Node current = openSet.poll();

            String currentKey = current.x + "," + current.y;

            

            if (current.x == goalX && current.y == goalY) {

                return reconstructPath(cameFrom, current);

            }

            

            if (visited.contains(currentKey)) continue;

            visited.add(currentKey);

            

            // Explore neighbors (up, down, left, right)

            int[][] directions = { /*{*/0,1/*}*/, /*{*/0,-1/*}*/, /*{*/1,0/*}*/, /*{*/-1,0/*}*/ };

            for (int[] dir : directions) {

                int newX = current.x + dir[0];

                int newY = current.y + dir[1];

                

                if (isValid(grid, newX, newY) && 

                    !visited.contains(newX + "," + newY)) {

                    Node neighbor = new Node(newX, newY, goalX, goalY);

                    openSet.add(neighbor);

                    cameFrom.put(newX + "," + newY, current);

                }

            }

        }

        return new ArrayList&lt;>(); // No path found

    }

}
```

#### **Greedy Best-First Analysis**



* **Time Complexity**: O(b^d) where b = branching factor, d = depth
* **Space Complexity**: O(b^d)
* **Optimality**: Not guaranteed - may find suboptimal paths
* **Completeness**: May get stuck in infinite loops without proper cycle detection

