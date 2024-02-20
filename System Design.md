# System Design Notes :

## Day 1:
Let's suppose we have started a Pizza shop with 1 chef, going forward we cater over all the problems we encounter using System design concepts.

### Driving real world solution of a real world problem:

1. Vertical Scaling: 
   If we start getting greater amount of orders , we initially ask out chef to work harder and faster and we pay the chef more. This is called Optimizing processes and increasing throughput using the same resource.
2. Preprocessing:
   We ask our chef to prepare the extra materials like batter and other things in non peak hours.
3. Horizontal Scaling:
   If we still get high amount of orders and chef has reached it epitome of hard work and cannot stretch more then we increase the amount of chefs in our store.
4. Resilience:
   What if there is a power outage in our store? We need to create backups and open another store somewhere else to avoid single point of failure. This makes the business Fault tolerant and gives quicker response.
5. Microservice architecture:
   If we have two orders coming in our store , one for pizza(higher volume) and other for garlic bread(lower volume) and we have 3 chefs. We distribute the garlic bread task to 1 chef and keep other two chefs for pizza. This is breaking requests to small services and then responding.
6. Load Balancing:
   We distribute our orders to specific stores depending upon which store will deliver the requested item quicker to that customer.
7. Decoupling: 
   We have a delivery boy to deliver the pizza to the customer. The delivery boy need not know what he is suuposed to deliver, be it pizza or anything. 
8. Logging and metrics: We keep log of all the metrics      involved in the business. This keeps our business tight and document handy.
9. Extensibility: 
    If we want to incorporate more items other than pizzas and garlic breads we can seemlessly start making and selling new items considering the volume of other orders whether a new chef is needed or not. This makes the business extensible.

### Definitions:
#### Scalability:

1. Vertical Scaling: 
   1. Increasing the capacity of a single source to handle the load.
   2. Single point of failure
   3. Consistent with data because all data transactions are from one resource only.
   4. There is a hardware limit.
2. Horizontal Scaling: 
   1. Increasing the resource count to handle the load.
   2. Its Resilient.
   3. Inconsistent with data because transactions can be from any resource at any time.
   4. Good Scalability. 

## Day 2:

### Load Balancing:
1. Let us assume you have a server which has a program which other users want to use.
2. Users will send a request and in return get a reponse from the server.
3. If we have too many users, to distribute the traffic you purhcase N number of servers.
4. To divide the traffic evenly on those N servers is called **Load Balancing**.

### Consistent Hashing:
1. Let us assume we have **n** number of servers.
2. When a request to the server is triggered by the user, it actually generates a request ID which is uniformly random.
3. This request id **[r]** is then sent to the hash function and a hashed value is generated **[h(r)]**.
4. The hashed value **[m]** is then divided by **n** and the remainder is the server index on which the request will be sent.
5. This is the basic process of how Consistent Hashing works.
   
### How consistent hashing works in practical world in distributed systems to balance the load?
1. Whenever a user sends a request, it has a unique identifier associated (e.g. username, userId, etc.), say **x**.
2. This unique identifier is hashed using a hash function, say **h(x)=y**.
3. The servers on the other hand also have unique identifiers associated with them (e.g IP address, etc.), say **m**.
4. This unique identifier is also hashed using the same hash function, say **h(m)=n**.
5. Imagine a virtual ring.
6. This ring actually stores the hashed server values and has a range associated with it.
7. For e.g if Server A, B and C have hashed values as 10, 40, 80 and total hash space is 0-100 which is total capacity of the ring.
8. Then server A has a range of 10-39, B has a range of 40-79 and C has a range of 80-9 (circle wrapping).
9. So when a user sends a request its hashed value **y** is searched in the clockwise direction in the ring such that the first hashed server value range is greater than or equal to **y** is found. 
10. The user hashed value falls under some server's range and that server is responsible for handling the request of the server.
11. A server can be added or removed easily only by hashing and placing the range in the virtual ring.
12. This evenly distributes the load on the ring and this is how consisitent hashing helps load balancing in distributed systems in real life practical scenarios.