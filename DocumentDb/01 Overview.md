(RESOURCE: https://www.documentdb.com/sql/demo)

DocumentDB is a fully managed, noSQL database service built for fast and predictable performance. High available, elastic 
 scaling, global distribution and ease of development. As a schema-free noSQL database, DocumentDB provides rich and familiar 
 SQL query capabilities. Yes, you heard me right, SQL query capabilities. This is the best part. DocumentDB guarantees that 99% 
 of your reads are served under 10 milliseconds and 99% of your writes are served under 15 milliseconds.
 
 So imagine a latency of just 10-15 milliseconds and a guaranteed associated with it. That makes it the best managed, noSQL database service out there. And this also makes it a great fit for web, mobile, gaming and even Internet of Things or IOT, and many other applications that need seamless scale and global replication. It's easily scalable, up or down, to meet your application needs. Data is stored on solid-state drives.


Yes, you heard me right, solid-state drives for low predictable latencies. It supports containers for storing JSON data. Multiregion capability. It can replicate data to all regions associated with their account. It provides regional failover with multihoming APIs. And it also has the ability to elastically scale throughput and provide global storage. 

SQL-like syntax:
It has the ability to store heterogeneous JSON documents and query through familiar SQL-like syntax. If you ever did link in .NET, it also uses a very SQL-like syntax. It's really for a lot of the DBAs who have their existing SQLs killed to feel comfortable querying a noSQL database. It also utilizes highly concurrent, lock-free, log-structured indexing technology which provides automatic indexing of all document content.

Now why is indexing important? Have you ever worked with a search database? And it could also be an in-memory search library, 
like Lucene or something like Solr or even something that scales elastically like Elasticsearch. The best part about that is 
indexing. When we index data, we can actually get what we want very quickly. More like an inverted index. And DocumentDB does 
that for you automatically for free. 

JavaScript execution within the database:
It can use standard JavaScript, which could be used to write stored procs, triggers, and user-defined functions. Yes, you heard 
me correct. You can actually write stored procedures in plain old JavaScript. The best part of the stored procs is that it 
takes the entire routine or the matter or the function of JavaScript and any time there's an exception, it rolls back the 
entire stored proc. So for example, you had a stored proc with 10 different things and the 8th thing had an exception, it's 
actually going to do a rollback.

Tunable consistency levels:
It provides four well-defined consistency levels, which we're going to discuss in detail a little later. There's strong, 
bounded staleness, eventual and session consistency. And again, this is fully managed. It removes the need for you to have your 
own team to manage this database. Microsoft Azure makes this a fully managed service. You do not need to manage any of the 
virtual machines. You do not need to deploy or configure any software, whatsoever, and you can manage the scaling 
programmatically.


Databases are automatically backed up and protected regionally. DocumentDB accounts can be easily added for the provision capacity needed which allows the user to focus on his application instead of operating and managing the database. Open by design. Users can begin working immediately with their existing skills and tools provided. Now if you know .NET and C#, you can actually use the .NET and C# API. If you know Java, you can use the Java API, and if you know JavaScript, you can actually use the Node.js API. And it also comes with an http RESTful interface. So you can use this with any language that has the ability to make REST calls. 

 Automatic indexing:
 The default settings automatically index all the documents in the database. Now, of course, it is an operation on top of a regular operation. So you also have the ability to remove it. If you do not want automatic indexing, you can actually make sure that that doesn't happen. If the user does not want to index everything, he can opt out of this.
 JSON data is managed in its well-defined database resources. These resources are replicated for high availability and are addressable by their logical URI, provides simple http based RESTful programming model for all resources.
 
  Database account is a unique namespace, providing the user access to Azure DocumentDB. Note, in order to create a database account, you must have an Azure subscription. All resources will be modeled and stored as JSON documents, which will be managed as items, which are really JSON documents containing metadata as feeds and feeds are collections of items.
 
 





 
 
