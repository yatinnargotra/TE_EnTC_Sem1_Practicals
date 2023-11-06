
# DBMS Practical Questions
* [Viva Questions](#coding)
* [Viva Answers](#tech) 
* [References](#ref)
____
<b name="coding">Viva questions</b><br/>

### Viva questions:

### DBMS Questions:

1. **Transaction State Diagram:**

   - **Question:** Explain the transaction state diagram in a database management system.

2. **Parallel Database and its Types, Delete and Select Particular Cell, Armstrong Axioms, Serialization, and Generalization:**

   - **Question:** What is a parallel database, and what are the different types of parallel database architectures? How can you delete a specific cell in a table, select a particular cell's value, and what are Armstrong Axioms and the differences between serialization and generalization in a database?

3. **Cluster Index:**

   - **Question:** What is a cluster index in a database, and how does it differ from other types of indexes?

4. **Trivial and Nontrivial Functional Dependency, Closure, and Serializable Transactions:**

   - **Question:** Explain the concepts of trivial and nontrivial functional dependencies in a relational database. How do you find the closure of a set of attributes, and how can you determine if a transaction is serializable?

5. **Different Types of Parallel Database Architectures:**

   - **Question:** List and explain the different types of parallel database architectures.

6. **Deleting a Particular Cell in a Table:**

   - **Question:** How can you delete a particular cell in a table within a database?

7. **Axioms in DBMS:**

   - **Question:** What are the axioms in a database management system, and how do they apply to database operations?

8. **Arithmetic Expressions in Selection and Projection:**

   - **Question:** How are arithmetic expressions used in operations like selection and projection in a relational database?

9. **Different Clauses in SELECT:**

   - **Question:** List some of the different clauses that can be used in a SELECT statement in SQL.

10. **Irrecoverable Schedule and How to Tackle It:**

    - **Question:** What is an irrecoverable schedule in the context of database transactions, and how can it be tackled or managed?

11. **Types of Parallel Database:**

    - **Question:** What are the different types of parallel databases, and what distinguishes them from each other?

12. **Deleting the First Row and (3,2) Element in a Table:**

    - **Question:** Given the table "xyz" with data, how can you delete the first row and the element at (3,2) i.e., 0 from the table?

I've formatted your code to make it more readable and structured in Markdown. You can copy and paste this into your document.
Let me know if you need further details or explanations on any of these tasks.

---
<b name="tech"></b>
<br/>
<i><u name="dsalg">Answers</u></i>

**1. Transaction State Diagram:**

- **Question:** Explain the transaction state diagram in a database management system.
- **Answer:** A transaction state diagram provides a visual representation of the various states a transaction can go through during its execution in a database management system. These states typically include:

    - **Active:** This is the initial state where the transaction starts its execution. In this state, the transaction can perform read and write operations on the database.

    - **Partially Committed:** Once the transaction has executed its operations and is ready to be committed, it enters this state. In this state, the changes made by the transaction are recorded but not yet visible to other transactions.

    - **Committed:** When a transaction is successfully completed and its changes are made permanent, it enters the committed state. In this state, the changes are visible to other transactions.

    - **Failed:** If any error or exception occurs during the execution of the transaction, it enters the failed state. In this state, the changes made by the transaction are rolled back, and the transaction cannot proceed further.

    - **Aborted:** In case of a failure, the transaction enters the aborted state, where it is terminated, and any changes made by it are completely rolled back.

Transaction state diagrams help in understanding the lifecycle of a transaction and are essential for ensuring the database's consistency and integrity.

**2. Parallel Database and its Types, Deleting and Selecting a Particular Cell, Armstrong Axioms, Serialization, and Generalization:**

- **Question:** What is a parallel database, and what are the different types of parallel database architectures? How can you delete a specific cell in a table, select a particular cell's value, and what are Armstrong Axioms and the differences between serialization and generalization in a database?

- **Answer:**

    - **Parallel Database and Types:** A parallel database is a database system that utilizes multiple processors or nodes to perform operations concurrently. Different types of parallel database architectures include:
  
        - **Shared-Memory:** In this architecture, multiple processors share a common memory, allowing them to access and process data in parallel. It's suitable for smaller datasets.
  
        - **Shared-Disk:** In a shared-disk architecture, multiple processors have their separate memory but share access to a common disk storage. This architecture is more scalable and suited for larger datasets.
  
        - **Shared-Nothing:** In this type, each processor or node has its own memory and disk storage, and they communicate to perform parallel operations. This architecture is highly scalable and fault-tolerant.

    - **Deleting and Selecting a Particular Cell:** To delete a specific cell in a table, you can use an SQL DELETE statement with a WHERE clause specifying the row and column that needs to be deleted. To select a particular cell's value, use an SQL SELECT statement with appropriate conditions for the row and column.

    - **Armstrong Axioms:** Armstrong's axioms are a set of properties used to infer functional dependencies in a relational database. They include:
  
        - **Reflexivity:** If a set of attributes A determines another attribute B, then it also determines itself (A -> A).
  
        - **Augmentation:** If A -> B, then adding attributes to A on both sides should still hold the dependency (A, C -> B, C).
  
        - **Transitivity:** If A -> B and B -> C, then it implies A -> C.
  
        - **Decomposition:** If A -> B, then it implies A -> B, C where C is a subset of B.

    - **Serialization and Generalization:** Serialization ensures that concurrent transactions do not interfere with each other and occur in a single-file sequence. Generalization is the process of abstracting data, typically using hierarchies or classifications to organize and simplify complex data structures.

**3. Cluster Index:**

- **Question:** What is a cluster index in a database, and how does it differ from other types of indexes?
- **Answer:** A cluster index in a database is a type of index that not only stores the values of indexed columns but also physically reorganizes the data in the table to match the order of the index. This means that the data rows in the table are physically stored in the same order as the index. This is in contrast to other types of indexes like non-clustered indexes, which do not dictate the physical order of the data.

The advantage of a cluster index is that it can significantly improve the performance of queries that retrieve data in the same order as the index. However, it's important to note that a table can have only one cluster index, and creating or changing a cluster index may require reorganizing the entire table, which can be resource-intensive.

**4. Trivial and Nontrivial Functional Dependency, Closure, and Serializable Transactions:**

- **Question:** Explain the concepts of trivial and nontrivial functional dependencies in a relational database. How do you find the closure of a set of attributes, and how can you determine if a transaction is serializable?

- **Answer:**

    - **Trivial and Nontrivial Functional Dependency:** In a relational database, a functional dependency occurs when one attribute or set of attributes uniquely determines another attribute. A functional dependency is considered trivial if the determining attributes already include the determined attribute (A -> A). Nontrivial functional dependencies involve one attribute or set of attributes determining another without including the determined attribute (A -> B, where A and B are distinct attributes).

    - **Closure of Attributes:** To find the closure of a set of attributes, you can use Armstrong's axioms. Starting with the given set of attributes, apply the axioms repeatedly to derive all the attributes that can be functionally determined by the original set. This set of attributes is the closure.

    - **Serializable Transactions:** To determine if a transaction is serializable, you can use techniques like Precedence Graph method or Conflict Serializable Schedules. If, in the resulting graph, there are no cycles, the transaction is serializable. Otherwise, it's not serializable, and you might need to adjust the schedule to make it serializable.

**5. Different Types of Parallel Database Architectures:**

- **Question:** List and explain the different types of parallel database architectures.
- **Answer:** Parallel database architectures include:

    - **Shared-Memory:** In this architecture, multiple processors or nodes share a common memory, allowing them to access and process data in parallel. It's suitable for smaller datasets but can become a bottleneck for larger ones.

    - **Shared-Disk:** In a shared-disk architecture, multiple processors have their separate memory but share access to a common disk storage. This architecture is more scalable than shared-memory and is suitable for larger datasets, as it avoids memory constraints.

    - **Shared-Nothing:** In a shared-nothing architecture, each processor or node has its own memory and disk storage. Processors communicate by message-passing and do not share resources. This architecture is highly scalable and fault-tolerant, making it suitable for large, distributed databases.

The key distinction between these types lies in how they handle memory and data storage. Shared-memory systems share memory resources, shared-disk systems share disk resources, and shared-nothing systems keep memory and disk resources separate. The choice of architecture depends on the specific requirements and scale of the database system.

**6. Deleting a Particular Cell in a Table:**

- **Question

** How can you delete a particular cell in a table within a database?
- **Answer:**  To delete a specific cell in a table within a database, you can use an SQL DELETE statement with a WHERE clause that specifies the condition for the row and column where the target cell is located. For example:

    ```sql
    DELETE FROM table_name WHERE column_name = 'target_value';
    ```

    This query will delete the row(s) that meet the specified condition, effectively removing the cell you want to delete.

**7. Axioms in DBMS:**

- **Question:** What are the axioms in a database management system, and how do they apply to database operations?
- **Answer:** In the context of a database management system, axioms typically refer to Armstrong's axioms, which are used to derive or prove functional dependencies in a relational database. These axioms are:

    - **Reflexivity:** If a set of attributes A functionally determines another attribute B, then it also determines itself (A -> A).

    - **Augmentation:** If A -> B, then adding attributes to A on both sides should still hold the dependency (A, C -> B, C).

    - **Transitivity:** If A -> B and B -> C, then it implies A -> C.

    - **Decomposition:** If A -> B, then it implies A -> B, C where C is a subset of B.

These axioms provide a foundation for identifying and understanding functional dependencies in a relational database, which is essential for normalization and data integrity.

**8. Arithmetic Expressions in Selection and Projection:**

- **Question:** How are arithmetic expressions used in operations like selection and projection in a relational database?
- **Answer:** Arithmetic expressions can be employed in SQL operations like selection and projection to filter, transform, or derive data during query execution.

    - **Selection:** In a selection operation (typically performed with the WHERE clause), you can use arithmetic expressions to filter rows based on numerical computations. For example, you can use arithmetic operators such as +, -, *, /, or functions like ABS(), to filter rows based on calculated values. For instance:

    ```sql
    SELECT * FROM table_name WHERE (column1 + column2) > 100;
    ```

    - **Projection:** In a projection operation, you can use arithmetic expressions to compute and return derived attributes in the result set. For example:

    ```sql
    SELECT column1, column2, (column1 * 1.1) AS computed_column FROM table_name;
    ```

    Here, a computed column is added to the result set using an arithmetic expression.

**9. Different Clauses in SELECT:**

- **Question:** List some of the different clauses that can be used in a SELECT statement in SQL.
- **Answer:** SQL SELECT statements can include various clauses to control and customize the query results. Some common SELECT clauses include:

    - **FROM:** Specifies the table or tables from which data is to be retrieved.
    - **SELECT:** Lists the columns to be retrieved from the specified table(s).
    - **WHERE:** Filters the rows returned based on a specified condition.
    - **GROUP BY:** Groups rows that have the same values into summary rows.
    - **HAVING:** Filters the grouped rows based on a specified condition.
    - **ORDER BY:** Sorts the result set based on specified columns and sorting order.
    - **LIMIT (or TOP):** Limits the number of rows returned in the result set.
    - **DISTINCT:** Ensures that only distinct (unique) values are returned.
    - **JOIN:** Combines rows from two or more tables based on a related column between them.

These clauses provide a high degree of flexibility for querying and manipulating data in SQL.

**10. Irrecoverable Schedule and How to Tackle It:**

- **Question:** What is an irrecoverable schedule in the context of database transactions, and how can it be tackled or managed?
- **Answer:** An irrecoverable schedule is a situation in a database where a committed transaction's changes are lost due to a system failure before those changes could be made permanent. This can lead to data inconsistencies and potential loss of critical data.

To tackle or manage irrecoverable schedules, several techniques can be employed:

- **Logging:** Implement a robust logging system that records all changes made by transactions. If a failure occurs, the system can use the logs to recover and reapply committed changes.

- **Checkpoints:** Periodically create checkpoints in the database to save the current state. In case of a failure, the system can roll back to the last checkpoint, ensuring that committed changes are not lost.

- **Redo/Undo Logs:** Maintain both redo and undo logs. Redo logs contain changes that must be reapplied in case of a failure, while undo logs contain changes that can be used to roll back uncommitted changes.

- **Database Replication:** Implement database replication to have multiple copies of the database so that if one fails, another can be used to recover committed changes.

Managing irrecoverable schedules is crucial for data consistency and integrity in database systems.

**11. Types of Parallel Database:**

- **Question:** What are the different types of parallel databases, and what distinguishes them from each other?
- **Answer:** There are several types of parallel database architectures, each with its own characteristics:

    - **Shared-Memory:** In this architecture, multiple processors or nodes share a common memory. It allows for efficient data sharing and processing but may not be as scalable as other types.

    - **Shared-Disk:** In a shared-disk architecture, multiple processors have their own memory but share access to a common disk storage. This architecture is more scalable than shared-memory and is suitable for larger datasets, as it avoids memory constraints.

    - **Shared-Nothing:** In a shared-nothing architecture, each processor or node has its own memory and disk storage, and they communicate via a network. This architecture is highly scalable, fault-tolerant, and is often used in massively parallel processing (MPP) systems.

The key distinction between these types lies in how they handle memory and data storage. Shared-memory systems share memory resources, shared-disk systems share disk resources, and shared-nothing systems keep memory and disk resources separate. The choice of architecture depends on the specific requirements and scale of the database system.

**12. Deleting the First Row and (3,2) Element in a Table:**

- **Question:** Given the table "xyz" with data, how can you delete the first row and the element at (3,2) i.e., 0 from the table?
- **Answer:** To delete the first row from the table "xyz," you can use the DELETE statement with a WHERE clause specifying a condition that matches the first row. Assuming you have a unique identifier like an ID, you can do:

    ```sql
    DELETE FROM xyz WHERE ID = 1;
    ```

    To delete the element at (3,2), you would typically use an UPDATE statement to modify the cell's value. Here's an example:

    ```sql
    UPDATE xyz SET C = NULL WHERE A = 3 AND B = 2;
    ```

    This sets the value of cell (3,2) to NULL. Please adjust the column names and conditions as per your specific table structure and values.
