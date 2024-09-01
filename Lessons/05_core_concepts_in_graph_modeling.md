# Lesson 5: Core Concepts in Graph Modeling

Welcome back, graph explorers! In this lesson, we’re going to dive deep into the core concepts of graph modeling. Just as an architect carefully designs a building, you will learn how to model entities, relationships, and properties in a graph. We’ll also explore how to apply these concepts to model business logic effectively. So grab your thinking caps, and let’s get started!

## Understanding Entities, Relationships, and Properties

### What Are Entities?

In the world of graph modeling, **entities** are the fundamental building blocks. An entity represents a distinct object or concept within your domain. For example, in a social network graph, entities could be users, posts, or comments. In a transportation network, entities could be cities, airports, or routes.

#### Characteristics of Entities:
- **Uniqueness**: Each entity should have a unique identifier (ID) that distinguishes it from other entities. For example, each user in a social network can be identified by a unique username or user ID.
- **Attributes**: Entities can have attributes (or properties) that provide additional information. For instance, a user entity might have attributes like name, age, and location.

### What Are Relationships?

**Relationships** (or edges) define how entities are connected to one another. They represent the interactions or associations between entities. For example, in a social network, a relationship could represent a friendship between two users or a comment made by a user on a post.

#### Characteristics of Relationships:
- **Directionality**: Relationships can be directed (one-way) or undirected (two-way). For example, if Alice follows Bob, the relationship is directed from Alice to Bob. If they are friends, the relationship is undirected.
- **Types**: Relationships can be categorized into different types based on their nature. For example, in a social network, you might have relationships like "follows," "likes," or "comments."

### What Are Properties?

**Properties** are key-value pairs associated with entities and relationships that provide additional context. They help to enrich the graph with meaningful information.

#### Examples of Properties:
- **Entity Properties**: A user entity might have properties like:
  - `username`: "alice123"
  - `age`: 30
  - `location`: "New York"

- **Relationship Properties**: A friendship relationship might have properties like:
  - `since`: "2020-01-01" (the date the friendship started)
  - `strength`: 5 (a score indicating how close the friendship is)

### Visualizing Entities and Relationships

Let’s visualize these concepts with a simple example:

```
Alice (User)
  | follows (relationship)
  |
Bob (User)
  | likes (relationship)
  |
Post 1 (Post)
```

In this graph:
- **Entities**: Alice and Bob are user entities, while Post 1 is a post entity.
- **Relationships**: Alice follows Bob, and Bob likes Post 1.
- **Properties**: You could add properties to each entity (e.g., age, location) and to each relationship (e.g., since, strength).

## Modeling Business Logic with Graphs

Now that we understand entities, relationships, and properties, let’s explore how to model business logic using graphs. Business logic refers to the rules and processes that govern how data is created, stored, and manipulated within a system.

### Why Use Graphs for Business Logic?

Graphs are particularly well-suited for modeling complex business logic due to their ability to represent intricate relationships and dynamic structures. Here are some reasons why graphs excel in this area:

1. **Natural Representation of Relationships**: Graphs allow you to model relationships intuitively, making it easier to understand how different entities interact.

2. **Flexibility**: Graph structures can evolve as business requirements change. You can easily add new entities and relationships without extensive restructuring.

3. **Rich Querying Capabilities**: Graph databases provide powerful query languages (like Cypher) that allow you to express complex business logic in a straightforward manner.

### Example: Modeling a Social Network

Let’s consider an example of modeling a social network. In this scenario, we want to represent users, their friendships, and the posts they like.

1. **Define Entities**:
   - **User**: Represents a person in the social network.
   - **Post**: Represents content created by users.

2. **Define Relationships**:
   - **Follows**: A directed relationship indicating that one user follows another.
   - **Likes**: A directed relationship indicating that a user likes a post.

3. **Define Properties**:
   - **User Properties**: Attributes like username, age, and location.
   - **Post Properties**: Attributes like content, timestamp, and likes count.
   - **Relationship Properties**: Attributes like since (for friendships) or strength (for likes).

### Visualizing Business Logic

Here’s how our social network graph might look:

```
Alice (User)
  | follows (since: "2020-01-01")
  |
Bob (User)
  | likes (strength: 5)
  |
Post 1 (Post)
```

In this graph:
- Alice follows Bob since January 1, 2020.
- Bob likes Post 1 with a strength of 5.

### Fun Activity: Model Your Own Business Logic!

Now it’s your turn to get creative! Choose a domain you’re familiar with (it could be a library system, an online store, or a project management tool) and model the business logic using graphs.

1. **Identify Entities**: List the key entities in your domain.
2. **Define Relationships**: Determine how these entities are connected. What relationships exist between them?
3. **Add Properties**: Think about what attributes are important for each entity and relationship.
4. **Draw the Graph**: Sketch your graph on paper or use a digital tool to visualize it.

### Conclusion

Congratulations! You’ve successfully navigated the core concepts of graph modeling. You’ve learned about entities, relationships, and properties, and explored how to model business logic effectively using graphs.

In the next lesson, we will dive into practical applications of graph-oriented programming, where you’ll get hands-on experience implementing graph structures and algorithms. Get ready to unleash your creativity and problem-solving skills in the world of graphs!

[Next Lesson](./06_overview_of_graph_databases.md)