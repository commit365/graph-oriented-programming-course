# Lesson 7: Introduction to Cypher Query Language

Welcome, aspiring graph wizards! In this lesson, we’re going to unlock the magic of **Cypher**, the powerful query language used with Neo4j. Just as a wizard needs a spellbook to cast spells, you will learn how to wield Cypher to query and manipulate graph data. By the end of this lesson, you’ll be able to write your own queries and uncover insights from your graph. Let’s dive into the enchanting world of Cypher!

## What is Cypher?

**Cypher** is a declarative query language specifically designed for working with graph databases. It allows you to express what data you want to retrieve or manipulate without needing to specify how to do it. This makes it intuitive and user-friendly, especially for those new to graph databases.

### Why Use Cypher?

- **Intuitive Syntax**: Cypher’s syntax is designed to be readable and expressive, making it easy to understand and write queries.
- **Focus on Relationships**: Cypher allows you to navigate and manipulate relationships naturally, reflecting how we think about connections in the real world.
- **Powerful Querying**: With Cypher, you can perform complex queries and traversals with minimal effort.

## Syntax and Structure of Cypher

Let’s break down the basic syntax and structure of Cypher so you can start crafting your own queries.

### 1. Nodes and Relationships

In Cypher, nodes are represented with parentheses `()`, and relationships are represented with arrows `->` or `<-`. Here’s how it looks:

- **Node**: `(Alice:User {name: 'Alice', age: 30})`
- **Relationship**: `-[:FRIENDS_WITH]->`

### 2. Basic Query Structure

A typical Cypher query consists of the following components:

- **MATCH**: Used to specify the pattern you want to find in the graph.
- **RETURN**: Specifies what data you want to retrieve from the matched pattern.
- **WHERE**: (Optional) Used to filter results based on certain conditions.

### Example Query

Here’s a simple Cypher query that matches users and returns their names:

```cypher
MATCH (u:User)
RETURN u.name;
```

In this query:
- `MATCH (u:User)` finds all nodes labeled `User`.
- `RETURN u.name` retrieves the names of those users.

### 3. Creating Nodes and Relationships

You can also create nodes and relationships using Cypher. Here’s how you can add a new user and a friendship relationship:

```cypher
CREATE (Alice:User {name: 'Alice', age: 30}),
       (Bob:User {name: 'Bob', age: 25}),
       (Alice)-[:FRIENDS_WITH]->(Bob);
```

In this query:
- `CREATE` is used to create new nodes and relationships.
- `Alice` and `Bob` are created as user nodes, and a friendship relationship is established between them.

## Basic Querying Techniques

Now that you understand the syntax and structure of Cypher, let’s explore some basic querying techniques that will help you retrieve and manipulate data effectively.

### 1. Finding Nodes

To find specific nodes, you can use the `MATCH` clause with conditions. For example, to find a user by name:

```cypher
MATCH (u:User {name: 'Alice'})
RETURN u;
```

### 2. Filtering Results

You can filter results using the `WHERE` clause. For example, to find users older than 25:

```cypher
MATCH (u:User)
WHERE u.age > 25
RETURN u.name;
```

### 3. Returning Multiple Properties

You can return multiple properties of a node by specifying them in the `RETURN` clause:

```cypher
MATCH (u:User)
RETURN u.name, u.age;
```

### 4. Counting Nodes

To count the number of nodes that match a certain pattern, you can use the `COUNT()` function:

```cypher
MATCH (u:User)
RETURN COUNT(u) AS totalUsers;
```

### 5. Traversing Relationships

You can traverse relationships to find connected nodes. For example, to find friends of a user:

```cypher
MATCH (u:User {name: 'Alice'})-[:FRIENDS_WITH]->(friend)
RETURN friend.name;
```

### 6. Using Aggregation Functions

Cypher supports various aggregation functions, such as `SUM()`, `AVG()`, and `COLLECT()`. For example, to find the average age of users:

```cypher
MATCH (u:User)
RETURN AVG(u.age) AS averageAge;
```

## Fun Activity: Write Your Own Cypher Queries!

Now it’s your turn to practice your Cypher skills! Follow these steps:

1. **Set Up Neo4j**: If you haven’t already, download and install Neo4j Desktop or use Neo4j Aura. Create a new project and database.

2. **Create Sample Data**: Use the following Cypher queries to create a simple social network graph:

   ```cypher
   CREATE (Alice:User {name: 'Alice', age: 30}),
          (Bob:User {name: 'Bob', age: 25}),
          (Charlie:User {name: 'Charlie', age: 35}),
          (Alice)-[:FRIENDS_WITH]->(Bob),
          (Bob)-[:FRIENDS_WITH]->(Charlie),
          (Alice)-[:FRIENDS_WITH]->(Charlie);
   ```

3. **Write Queries**: Try writing your own Cypher queries to:
   - Find all users in the graph.
   - Retrieve the names of all friends of Alice.
   - Count the total number of users.
   - Find the average age of users.

4. **Experiment**: Feel free to modify the data or add new users and relationships. See how your queries change based on the graph structure!

## Conclusion

Congratulations! You’ve successfully unlocked the basics of Cypher query language. You’ve learned about its syntax and structure, as well as various querying techniques to retrieve and manipulate graph data.

In the next lesson, we will dive deeper into advanced Cypher queries and explore how to perform complex operations on your graph. Get ready to level up your graph querying skills and unleash the full potential of Cypher!

[Next Lesson](./08_advanced_querying_techniques_with_cypher.md)