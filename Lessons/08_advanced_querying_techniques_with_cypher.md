# Lesson 8: Advanced Querying Techniques with Cypher

Welcome back, graph adventurers! You’ve mastered the basics of Cypher, and now it’s time to level up your skills with some advanced querying techniques. In this lesson, we will explore the powerful capabilities of Cypher, including pattern matching, complex queries, aggregation, and filtering. Get ready to unleash the full potential of your graph database!

## What is Advanced Querying?

Advanced querying in Cypher allows you to express complex relationships and retrieve intricate data patterns from your graph. With these techniques, you can perform sophisticated analyses, uncover hidden insights, and manipulate your graph data with precision. Let’s dive into the exciting world of advanced querying!

## 1. Pattern Matching

### What is Pattern Matching?

**Pattern matching** is one of the most powerful features of Cypher. It allows you to specify the structure of the data you want to retrieve by describing the nodes and relationships in a visual way. This makes it easy to express complex queries that reflect the relationships in your graph.

### Basic Pattern Matching

Let’s start with a simple example. Suppose we have the following graph:

```
(Alice)-[:FRIENDS_WITH]->(Bob)
(Alice)-[:FRIENDS_WITH]->(Charlie)
(Bob)-[:FRIENDS_WITH]->(David)
(Charlie)-[:FRIENDS_WITH]->(David)
```

To find all friends of Alice, you can use the following query:

```cypher
MATCH (Alice:User)-[:FRIENDS_WITH]->(friend)
RETURN friend.name;
```

### Complex Pattern Matching

You can also match more complex patterns. For example, to find friends of friends of Alice (i.e., Alice's friends and their friends), you can use:

```cypher
MATCH (Alice:User)-[:FRIENDS_WITH]->(friend)-[:FRIENDS_WITH]->(fof)
RETURN fof.name;
```

In this query:
- `MATCH (Alice:User)-[:FRIENDS_WITH]->(friend)` finds Alice's friends.
- `-[:FRIENDS_WITH]->(fof)` finds friends of those friends.

### Optional Matching

Sometimes, you may want to include nodes that may or may not exist in your query results. You can use the `OPTIONAL MATCH` clause for this purpose. For example, to find all friends of Alice and their friends, even if some friends don't have friends:

```cypher
MATCH (Alice:User)-[:FRIENDS_WITH]->(friend)
OPTIONAL MATCH (friend)-[:FRIENDS_WITH]->(fof)
RETURN friend.name, fof.name;
```

## 2. Aggregation in Cypher

### What is Aggregation?

**Aggregation** allows you to perform calculations on your data, such as counting, summing, or averaging. Cypher provides several built-in aggregation functions that you can use to analyze your graph data.

### Common Aggregation Functions

1. **COUNT()**: Counts the number of items in a result set.
2. **SUM()**: Sums up the values of a specified property.
3. **AVG()**: Calculates the average of a specified property.
4. **COLLECT()**: Collects values into a list.

### Example: Counting Nodes

To count the total number of users in your graph, you can use:

```cypher
MATCH (u:User)
RETURN COUNT(u) AS totalUsers;
```

### Example: Summing Values

If you have a property on your nodes representing the age of users, you can sum their ages:

```cypher
MATCH (u:User)
RETURN SUM(u.age) AS totalAge;
```

### Example: Averaging Values

To find the average age of users:

```cypher
MATCH (u:User)
RETURN AVG(u.age) AS averageAge;
```

### Using COLLECT()

You can use `COLLECT()` to gather values into a list. For example, to collect the names of all friends of Alice into a list:

```cypher
MATCH (Alice:User)-[:FRIENDS_WITH]->(friend)
RETURN COLLECT(friend.name) AS friendsList;
```

## 3. Filtering in Cypher

### What is Filtering?

**Filtering** allows you to refine your query results based on specific criteria. In Cypher, you can use the `WHERE` clause to filter nodes and relationships.

### Basic Filtering

For example, to find all friends of Alice who are older than 25:

```cypher
MATCH (Alice:User)-[:FRIENDS_WITH]->(friend)
WHERE friend.age > 25
RETURN friend.name;
```

### Combining Filters

You can combine multiple conditions using logical operators such as `AND`, `OR`, and `NOT`. For example, to find friends of Alice who are either older than 25 or live in New York:

```cypher
MATCH (Alice:User)-[:FRIENDS_WITH]->(friend)
WHERE friend.age > 25 OR friend.location = 'New York'
RETURN friend.name;
```

### Using Regular Expressions

Cypher also supports regular expressions for more advanced filtering. For example, to find users whose names start with "A":

```cypher
MATCH (u:User)
WHERE u.name =~ '^A.*'
RETURN u.name;
```

## Fun Activity: Create Your Own Advanced Queries!

Now it’s your turn to practice your advanced Cypher skills! Follow these steps:

1. **Set Up Your Graph**: If you haven’t already, create a graph in Neo4j with at least 5 users and various relationships. You can use the following queries to set up sample data:

   ```cypher
   CREATE (Alice:User {name: 'Alice', age: 30}),
          (Bob:User {name: 'Bob', age: 25}),
          (Charlie:User {name: 'Charlie', age: 35}),
          (David:User {name: 'David', age: 28}),
          (Eva:User {name: 'Eva', age: 22}),
          (Alice)-[:FRIENDS_WITH]->(Bob),
          (Alice)-[:FRIENDS_WITH]->(Charlie),
          (Bob)-[:FRIENDS_WITH]->(David),
          (Charlie)-[:FRIENDS_WITH]->(David),
          (Eva)-[:FRIENDS_WITH]->(Alice);
   ```

2. **Write Advanced Queries**: Try writing your own advanced Cypher queries to:
   - Find all friends of Alice who are older than 25.
   - Count the total number of friends each user has.
   - Find friends of friends of Bob.

3. **Experiment**: Feel free to modify the data or add new users and relationships. See how your queries change based on the graph structure!

## Conclusion

Congratulations! You’ve successfully unlocked the advanced querying techniques of Cypher. You’ve learned about pattern matching, complex queries, aggregation, and filtering. 

In the next lesson, we will dive into practical applications of graph-oriented programming, where you’ll get hands-on experience implementing graph structures and algorithms. Get ready to unleash your creativity and problem-solving skills in the world of graphs!

[Next Lesson](./09_introduction_to_gremlin_and_other_query_languages.md)