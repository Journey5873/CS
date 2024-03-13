# Caching Strategies

## What is Caching?

In computing, a cache is storage that stores data so that future requests for the same data can be retrieved faster. Caching is the process of storing copies of files in that cache or temporary storage location, so that they can be accessed more quickly.

❕Cache hit: If the requested data is in the cache, it retrieves the data right away from the cache.
❕Cache miss: If the requested data is not in the cache, it retrieves the data from the database (DB).

🚨 When using a cache, the common issue is the problem of data consistency.

Data consistency refers to data being accurate and coherent across databases, systems, and applications. There might be issues of inconsistency between the cache and the database. Therefore, it is essential to implement appropriate cache read and write strategies.

## **Read Cache Strategy**

### **Cache-Aside (Lazy Loading)**

![Untitled](https://github.com/Journey5873/CS/assets/99030586/098c6af8-5227-4fc1-afd8-2522b283fe76)

A cache-aside is the most common caching strategy. In this strategy, the application manage the cache.

1. When the application requests data from the database, it checks the cache first.
2. If the data is in the cache (a cache hit), the cached data is returned to the caller.
3. If the data is not in the cache (a cache miss), the database is queried for the data. Then, application stores that data retrieved from the database, and the data is returned to the caller.

🏆 Advantages of Cache-Aside

- The cache contains only data that the application actually requests, which helps keep the cache size cost-effective.

🤔 Disadvantage of Cache-Aside

- The data is loaded into the cache only after a cache miss, incurring some overhead during the initial response time.
- It requires careful management of the cache to ensure that it stays up-to-date.

### **Read Through**

![Untitled (1)](https://github.com/Journey5873/CS/assets/99030586/ccbedfe5-02e0-4285-965d-e04b49a42218)

In this strategy, the cache is used as the primary data source. The application does not interact with the database.

1. When the data is requested, the application checks the cache first. 
2. If the data is in the cache (a cache hit), the cached data is returned to the caller.
3. If the data is not in the cache (a cache miss), it is retrieved from the database and stored in the cache.

🏆 Advantages of Read-Through

- This strategy is suitable when the database is slow or when the data is frequently read but rarely updated.
- Since the cache handles the data loading, it can reduce the load on the client.

🤔 Disadvantage of Read-Through

- Similar to Cache-Aside, data is loaded into the cache only after a cache miss, incurring some overhead during the initial response time.
- It requires careful management of the cache to ensure that it stays up-to-date.

## **Write Cache Strategy**

### **Write-Through**

![Untitled (2)](https://github.com/Journey5873/CS/assets/99030586/540cc490-ce26-493d-8929-bbecdd508e80)

In this strategy, data is written to both the cache and the database simultaneously. And when the data is updated, it is stored in the cache and database at the same as well.

1. The data is initially stored in the cache.
2. The data is then stored in the database.

🏆 Advantages of Write-Through

- The datas in the cache is always up-to-date.

🤔 Disadvantage of Write-Through

- Since all data is stored in the cache, data that might be not used could also be present in the cache. This results in a larger and more expensive cache.
- When the data is updated, it is stored in both the cache and the database simultaneously. Due to this, there is some overhead incurred during the update process.

### Write-Behind

![Untitled (3)](https://github.com/Journey5873/CS/assets/99030586/1db06d66-4eeb-4cfd-842e-5290c7ca3e0f)

In this strategy, data is first stored in a cache instead of directly in the database. The data accumulates in the cache and, at a specific point in time, it is written to the database.

1. All data is stored in the cache.
2. After a certain amount of time, the data which are in the cache is stored in the database.

🏆 Advantages of Write-Behind

- Write operations are faster because the data is stored at once.

🤔 Disadvantage of Write-Behind

- If the cache is not properly managed, there might be issues with data inconsistency.

### **Write-Around**

![Untitled (4)](https://github.com/Journey5873/CS/assets/99030586/b181da14-adb5-42ba-9da3-3852d0ebe911)

All data is stored in the database. Only when a cache miss occurs, data is stored in the cache.

1. All data is stored in the database.
2. When application request data, it read the data from the cache.
3. If there are not data in the catch, it read the data from the database.
4. Application write the data in the cache.

🏆 Advantages of Write-Around 

- This strategy is very fast.

🤔 Disadvantage of Write-Around

- If the data is updated in the database, there might be issues with data inconsistency.
- It may lead to higher read latencies when there is a cache miss.

---

📂 Reference

[What is Caching and How it Works | AWS](https://aws.amazon.com/caching/)

[What is caching? | How is a website cached? | Cloudflare](https://www.cloudflare.com/learning/cdn/what-is-caching/)

[Cache Strategies](https://medium.com/@mmoshikoo/cache-strategies-996e91c80303)

[Caching patterns - Database Caching Strategies Using Redis](https://docs.aws.amazon.com/whitepapers/latest/database-caching-strategies-using-redis/caching-patterns.html)

[Top 5 Caching Patterns](https://newsletter.systemdesign.one/p/caching-patterns)

[Three Popular Caching Strategies](https://linkedin.com/pulse/three-popular-caching-strategies-donny-widjaja-mspm-cspo)
