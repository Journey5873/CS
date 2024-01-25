# Transaction

## What is a database transaction?

A database transaction is a sequence of multiple operations performed on a database, all treated as a single logical unit of work. A transaction can either be committed, in which case the changes are saved in the databases/tables, or rolled back. Rolling back a transaction returns the databases to a previous state, undoing any changes made during the transaction.

So a transaction can be a unit of work to restore the database in case of a failure or failover.

## **What are ACID properties?**

1. Atomicity
    
    A transaction should be reflected in databases as "all or nothing.”
    
    When a transaction is committed, the database either completes the transaction successfully or rolls it back so that the database returns to its original state.
    
2. **Consistency**
Consistency ensures that transactions maintain the integrity, regardless of whether is succeeds or fails. 
Transactions can only alter affected data in a way that is authorized by the database engine, ensuring that a consistent view of the data is maintained at all times.
3. Isolation
    
    With multiple concurrent transactions running at the same time, each transaction should be kept independent without affecting other transactions executing simultaneously.
    
    To ensure isolation, ‘Lock & Unlock’ is used.
    
4. Durability
    
    When transactions ended and committed successfully, those should be reflected permanently.
