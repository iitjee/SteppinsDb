The two most important factors when choosing a NoSQL database are scalability and performance. Which is why DocumentDB is such an exciting solution. DocumentDB scales exceptionally well and is fully managed, making our job as a developer much more stream line.

 With the advent of mobile, tablet, and Internet of Things, a relational database management system is not the best to scale out. SQL databases, in general, are great at scaling up but not scaling out. NoSQL or not only SQL, databases are geared towards outer scaling.

The intent is simple. Scale out with commodity level machines that don't require high processing power, memory, or even hard 
drive space. Amazon claims that just an extra 1/10 of a second on their response times will cost them one percent in sales. And 
Google claims that half a second increase in latency, which is just 500 milliseconds, causes their traffic to drop by a fifth. 
And that's a few billion dollars. There are psychological studies that indicate that a user starts getting impatient if the web 
request on the screen takes more than just 200 milliseconds, which is really nothing more than a fifth of a second.

Competitive advantage in today's online world is about 250 milliseconds. If your website is faster than the competitor's 
website by just 250 milliseconds on average, you might have already won the game. 

In order to understand databases, CAP theorem needs to be understood. And CAP theorem stands for C as in consistency, A as in 
availability, and P as in partition tolerance. 
- Consistency really means that with every read, you're going to receive the most recent write or you're going to get an error. 
- Availability means that every request receives a response, without the guarantee that it contains the most recent version of 
the information. 
- And partition tolerance means that the system continues to operate despite an arbitrary number of messages being dropped by 
the network between nodes. 

Gilbert and Lynch have a white paper that says that no set of failures less than the total network failure is allowed to cause 
the system to respond incorrectly. So here is a triangle, and just to be clear that this is a very high level description of 
these concepts.

- Fallacies of distributed computing. Now if you've really never worked on a system that involves multiple servers, the first 
time you try to work on distributed computing, you might assume certain things. And those could be that network is reliable, 
'cause you may never assume the network is going to break, and if the network breaks, what really happens?
You might assume that the latency is zero, which actually never is. Anytime you add a hop, even that means a web server or a 
database server, you're going to have to see who is the user.

Someone who's going to be on a mobile phone while he's driving a car is going to have a very different latency than someone 
sitting on a fiber-optic gigapower network. At the same time, the servers are going to require bandwidth and depends on how 
much traffic you have. Bandwidth could be limited in the entire data center. And network is secure, which is another fallacy. I 
would highly recommend reading this article. In 1994, Peter Deutsch drafted about seven assumptions that architects and 
designers of distributed systems are likely to make which prove wrong in the long run. (https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing)
And in 1997, James Gosling added another one of these fallacies. Now these are collectively known as Eight Fallacies of Distributed Computing, but this is a very insightful article about making sure that we do not assume these things when we are designing a system that needs to scale out and serve needs for millions and millions of users.

Another fallacy is that topology doesn't change. So you might think that you have a master and two slaves, but for some 
reasons, those slaves may not have a way to communicate to the master.
And in such a situation, both these slaves could promote themselves to be a master in case the master was dead, just because 
they have no way to communicate with each other, and it's called a split brain scenario, and all this is really because of the 
change in topology. And then the other three are that we assume that there's one administrator and there is really no transport 
cost and the network is homogenous, which is never usually the case.

So now we'll compare SQL versus NoSQL and talk about the concepts that are important for scalability.
(there's a graph in vid)
Memcached, which is really the fastest Key Value pair, it is very good at Scalability and Performance, but barely has any Depth of Functionality. In fact, it's not even like Redis. Redis at least has data structures. Memcached doesn't. So this is really on extreme ends. 

NoSQL vs. Relational. A lot of people ask me this question that we don't really have joins in NoSQL database. Well, the 
question is, do you really need it? Most of the things are flat documents in a NoSQL database, and if you really need to join 
between two flat documents, you can always do that in a new application. Just because it doesn't have joins doesn't mean it has 
any less functionality than a relational database. 
The second question that's asked is about transactions. RDBMS is very good for concurrency integrity. We can also say ACID 
transactions. Atomicity, Consistency, Isolation, and Durability. And that is  definitely something that may be lacking in a 
NoSQL work. However, when we do our applications, we use a unit of work pattern. That may have a transaction or multiple 
transactions as part of their pattern. And that pattern is usually used at the application level. And we can still do that even 
with a NoSQL database whenever needed. 

The real need for a NoSQL database comes when we need scalability. And I'm not trying to say that NoSQL is a complete 
replacement for a relational database. There's a lot of things relational database is very good at, and one of them is 
transactions. The other thing could be security, encryption, and a lot of other things. So if you have data like your social 
security number, your HIPAA compliance data, BCI compliant data, a lot of that still belongs in the relational database.

However, if you have tons of comments on your website, on every single product, that data probably belongs in NoSQL database. 
If you have to do second level caching, that data probably belongs in another NoSQL database, like Redis or Memcached. If you 
want to do some kind of exclusive Google-like search, that data probably belongs in another NoSQL database, which is more like 
a search database, like Solar, Elasticsearch, FAST, or anything else. 

We also have to understand that we don't just have highly structured data. We also have semi-structured data, and also 
unstructured data, and a lot of blog kind of data might really belong in a NoSQL rather than a relational database. And that 
might include your pictures and sometimes even videos. And one of the most important reasons could also be the cost, where we 
can use cheap and plentiful memory in case of NoSQL databases. 

 Here's a really good example on couchbase.com, which talks about scalability and explains how SQL just wouldn't scale beyond that point.

Can we try to scale in RDBMS? We definitely can. However, it's very highly distruptive to re-shard, and we start losing the 
benefits of relational model. We also have to create and maintain the schema on every server. One of the examples is let's say 
you have all in command on your integer ID field, and you go in from one server to another. Now we might have to change the ID 
and create a GUID. Which is the right solution in order for it to make and work correctly, because we don't want duplicate IDs.

But at the same time, you might have a reason to actually keep everything as an integer and not really like a GUID. But that 
problem may not occur in case of a NoSQL, because you can use a composite key and you can start using all the sharding 
capabilities, and a lot of other things. Again, the problem is not scaling in RDBMS, the problem is scaling our system, and we 
can always do that with a combination, often RDBMS with some NoSQL databases.

Another thing that we talk about is denormalizing in RDBMS, which is one practice that is hard to understand. Because really 
what that means is denormalizing a relational database management system. Or creating a non-relational relational database 
management system. You can already understand how that sounds. So some of the other benefits are that we can go completely 
schemaless. So for example, in case of in RDBMS we have a table that has certain columns, and for some reasons, we need to add 
another column.

What happens to the existing data? A lot of times, we have to go back and add a lot of nulls. But in case of a NoSQL, it 
doesn't really matter. We can have a person object, with a name and age, and then the next record could be another person 
object with name, age, and date of birth. And the third record could actually have name, age, and date of birth with a 
completely different format. These are things that are not very easy to be done in a relational database, but NoSQL handles it 
really well.

It comes with autosharding, as we talked about earlier, and it also provides you distributed querying. With tons of your 
servers out there, all you do is use the distributed querying model, and it gets you the data you need. And it also has 
integrated caching with it. And reads are a lot faster than SQL for the most part. It's a common misconception that there is 
only one kind of NoSQL database, and it's exactly opposite to SQL or RDBMS.


In fact, there are many kinds of different NoSQL databases, and a lot of them are good at one thing, and they do that one thing really well. The first one is key value pair, which could be like Memcached, which is very quick on retrieval. As long as you know the key, you're going to get the value really quickly. The second one is more like an ordered key value pair that you kind of have this key value pairs, but they somehow also know about each other, and you can order them. And then the third one is a wide-column store. We're looking at something like a big table.

Number four is really two different ones, but they are document databases. One could be a regular document database, where the key is more important, more like a MongoDB, Cassandra, Riak, or something like that. And the second one is more like full text search, where the value part is more important, where you can have search like Lucene, Solar, Elasticsearch, FAST, or anything else. Number fifth is graph databases, something like a Neo4j, which is very good at relations because it has links to each other.

What I mean by that is every single entity could be linked to multiple entities, and they in return could be linked to a lot of other entities. Clearly more like a graph database. And number six is more like an object database where that particular object, could be adjacent object or whatever, becomes the first-class citizen, and that's how it's handled. And there's a lot of other different kinds.
