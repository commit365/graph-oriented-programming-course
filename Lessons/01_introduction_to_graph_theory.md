# Lesson 1: Introduction to Graph Theory

Welcome to the fascinating world of graph theory! In this lesson, we will embark on an adventure through the fundamental concepts of graphs, exploring their definitions, types, and applications. By the end of this lesson, you will not only understand the basic terminology but also appreciate the beauty and utility of graphs in solving real-world problems.

## What is a Graph?

At its core, a graph is a collection of **nodes** (also called vertices) connected by **edges**. Think of a graph as a map of relationships, where each node represents an entity, and each edge represents a connection between those entities. 

### Definitions and Terminology

- **Node (Vertex)**: A fundamental unit of a graph that represents an entity. For example, in a social network graph, each person is a node.

- **Edge**: A connection between two nodes. Edges can represent various types of relationships, such as friendships, communications, or transactions.

- **Directed Graph**: In a directed graph, edges have a direction, meaning they go from one node to another. This is like a one-way street where you can only travel in one direction. For example, if node A points to node B, you can travel from A to B, but not from B to A.

  Directed Graph Example

- **Undirected Graph**: In an undirected graph, edges have no direction. This means you can travel in both directions between nodes, just like a two-way street. For example, if there is an edge between nodes A and B, you can go from A to B and from B to A.

  Undirected Graph Example

### Types of Graphs

Graphs come in various shapes and sizes, each suited for different applications. Let’s explore some of the most common types:

1. **Weighted Graph**: In a weighted graph, each edge has a numerical value (or weight) associated with it. This weight can represent distance, cost, or any other metric. For example, in a road network graph, the weight might represent the distance between two cities.

   Weighted Graph Example

2. **Unweighted Graph**: In an unweighted graph, edges do not have weights. All edges are treated equally, which simplifies many algorithms. For example, in a social network graph, you might simply want to know if two users are connected, regardless of the strength of their relationship.

3. **Cyclic Graph**: A cyclic graph contains at least one cycle, which is a path that starts and ends at the same node. Cycles can represent feedback loops in systems, such as in a network of dependencies.

   Cyclic Graph Example

4. **Acyclic Graph**: An acyclic graph does not contain any cycles. A common example of an acyclic graph is a **tree**, which is a special type of graph used to represent hierarchical structures, such as family trees or organizational charts.

   Acyclic Graph Example

### Real-World Applications of Graphs

Graphs are not just theoretical constructs; they are everywhere in the real world! Here are some exciting applications of graph theory:

- **Social Networks**: Graphs model relationships between users, allowing us to analyze connections, find influencers, and recommend friends.

- **Transportation Networks**: Graphs represent routes and connections in transportation systems, helping to optimize travel routes and reduce congestion.

- **Recommendation Systems**: Graphs help in recommending products or content based on user preferences and interactions.

- **Biological Networks**: In biology, graphs can model interactions between proteins, genes, and other biological entities, aiding in the understanding of complex systems.

### Fun Activity: Create Your Own Graph!

Now that you have a basic understanding of graph theory, let’s put your knowledge to the test! Grab a piece of paper and draw your own graph representing your social network. 

1. **Nodes**: Represent yourself and your friends as nodes.
2. **Edges**: Draw edges to represent friendships. Use directed edges if you want to show who follows whom on social media.
3. **Weights**: If you want to get fancy, assign weights to your edges based on how close you feel to each friend (e.g., 1 for acquaintances, 5 for best friends).

### Conclusion

Congratulations! You have taken your first steps into the world of graph theory. You’ve learned about the fundamental definitions and terminology, explored different types of graphs, and discovered their real-world applications. 

In the next lesson, we will dive deeper into graph representations and how to implement them in programming. Get ready to unleash the power of graphs in your coding journey!

[Next Lesson](./02_understanding_graph_structures.md)