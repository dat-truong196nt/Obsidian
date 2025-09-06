A transaction is an indivisible unit of work.

- ACID properties:
    - **Atomicity**
        
        Each transaction is all or nothing.  
        - A transaction combines various processes (add, subtract, remove, ....), if any of this fall → DB will revert back to the previous state.  
        - Ex: We have a back account and want to transfer 1K from user A to user B. We have 3 things todo:  
        + Update -1K from A.  
        + Update +1K to B.  
        + Add a transfer history: transaction A to B in 1K.  
        
    - Consistency
        
        Any transaction will bring the database from one **valid** state to another  
        The operation must be done in a predictable way.  
        Ex: Bank account’s money can’t be negative.
        
    - Isolation
        
        Executing transactions concurrently has the same results as if the transactions were executed serially  
        Each transaction is isolated, and can’t affect other transactions.  
        
    - **Durability**
        
        Once a transaction has been committed, it will remain so
        
- Scale
    
    Master: read/write || Slave: read-only.
    
    - Replication
        
        - Master-slave replication
            
            How:  
            - 1 master - many slaves.  
            - master will replicate the writing to all slaves.  
            - Once master down, a slave will be promoted to master.  
            Disadvantages:  
            - Need algorithm to promote master.  
            - Once master down, the system is in read-only mode
            
        - Master-master replication
            
            How:  
            - many masters.  
            - data will be replicated between masters.  
            Advantages:  
            - Once a master goes down, the system can still read/write.  
            Disadvantages:  
            - Need a load balancer to direct the read/write.  
            - Violate Consistency (ACID), the state can be wrong.  
            - Confix between masters.
            
        
        Disadvantages:  
        - If a master goes down before writing sync → data lost.  
        - Need replication → More write → Can’t do much read.  
        - More slaves → More replicate → More lag.  
        -  
        - More hardware, more complex
        
    - **Federation**
        
        How:  
        - Split data by function.  
        Advantages:  
        - Less traffic to each node → Less replication lag.  
        - More data can fit into memory.  
        - Write in parallel.  
        Disadvantages:  
        - Hard to join.  
        - Update logic where to read/write from.  
        -
        
    - **Sharding**
        
        How:  
        - each database can only manage a subset of the data.  
        Disadvantages:  
        - Data distribution is lopsided in a shard(node).  
        - Complex joining data.
        
    - **Denormalization**
        
        How:  
        - Redundant copies of the data are written in multiple tables to avoid expensive joins  
        Why:  
        - In most systems, reads can heavily outnumber writes 100:1 or even 1000:1.  
        - A read resulting in a complex database join can be very expensive  
        Advantages:  
        - Improve read performance due to less expensive table join.  
        - When data becomes distributed, managing joins increases the complexity.  
        Disadvantages:  
        - Data is duplicated.  
        - Hard to make redundant copies sync.  
        - Worst writing.
        
- **SQL tuning**
    
    Benchmark: Simulate high-load situations (A lot of queries in a time).  
    Profile: Create a long-time query to test performance.