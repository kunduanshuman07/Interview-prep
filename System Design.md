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
13. Consistent hashing removes the fear of having duplicate requests being made to any server.


### Message Queue: 
1. Let us assume we have 4 servers which are currently in process of executing requests from users.
2. Every task being assigned to the server is inside a **database** which logs the tasks with the server id which is executing it and the status of the task which yes/no (exceuted or not).
3. If one of the servers goes on a power outage or failure, What will happen to the unexecuted tasks assigned to it?
4. We have a heartbeat notifier + load balancer with us which combined is termed as Message Queue.
5. The heartbeat notifier checks the heartbeat of servers and when a server fails it actually goes into the DB and collects all the unexceuted tasks from all the server id's.
6. The load balancer distributes all the tasks evenly to the remaining servers.
7. What if server 4 fails and server 3 is working on executing task id 3 and load balancer picking up all the unexecuted tasks picks up task id 3 as well and what if assigns it back to server 3 again where task id 3 is in process. This is duplicacy of tasks. This fear is taken care by consistent hashing inside the load balancer which does not allow duplicate tasks being created.


## Day 3:

### Monolith architecture:
1. The entire application is designed, deployed as a single unit.
2. UI interface, business logic, data access layer are all at one place.
3. It can be horizontally scaled but its very difficult to do so.
4. Complete architecture uses the same tech stack.
5. Changes on one part of the application often requires changes in other parts as well.
6. When a new team member comes, he/she needs to go through the complete code to understand the application athough he/she will work on one small part.
7. Have procedural calls which are fast reason being the calls are within one server(local).

### Microservice architecture:
1. The entire application is divided into small services which are independent of one other.
2. Every service has its own simple business logic and probably a seperate database which decomposes it to a simple architecture.
3. It can easily be scaled.
4. Because of the services being independent of one other, mixture of tech stacks can be used.
5. When a new team member comes and he/she is assinged a specific task then he needs to just understand the small code logic of the service he/she will be working on.
6. Some times slower in request processing because the calls of one service to other is not local rather they are remote which can take some time.
7. As they grow it becomes complex to manage the architecture.
8. Requires more planning and a good architect to design.


### Database Sharding:
1. It is a way of partition your database in smaller more manageable chunks called shards using some unique sharding key or criteria.
2. Every shard is distributed to multiple database servers.
3. Every shard contains smaller range of the complete data.
4. Servers are assigned tasks to query data base from specific shards.
5. After sharding the performance of the over all request response process increases, the reason being parallel querrying in the database shards.
6. For example in a dating app we shard the database based on location.
7. Generally used in Bigger applications where there is huge traffic and high volume of data being fetched at once.
8. There are some challenges like Data consistency, Re-routing when a shard fails (This fear can be avoided using Master Slave architecture where the slave continously copies its master, read permissions are from slave and write permissions are only into Master, when master fails, the slaves chose one master amongs themselves.), Joins processing among two or more shards can be slow.

## Day 4:

### HTTP:
1. HTTP: Hyper text transfer protocol
2. It's a set of rules used by systems to access and transfer any type of data across internet (world wide web);
3. It uses port 80, what is a port? Port is like a door to enter or exit a building so accessing and providing stuff internet using HTTP uses port 80, that is gate number 80 to internet building.
4. Uses stateless client server communication, i.e after one communication both client and server forgets about that happened.

### HTTPS:
1. Works similar to HTTP with a extra S in the end which serves Security over transferring private data like passwords.
2. It converts the private data to codes which only client and server understands.

### TCP/IP:
1. Transmission Control Protocol
2. Works just one layer below HTTP/HTTPS.
3. It helps the data being transferred to client from server complete a smooth process by splitting the data into packets which is more understandable and manageable.


### TCP Model: Helps communicate between network devices over the internet
1. Application layer: This layer is responsible for requesting web pages from server using HTTP.
2. Transport layer: This layer is responsible for establishing a connection between client and server uses TCP.
3. Network layer: Also known as IP layer. It is responsible for breaking down data into packets and giving each packet the IP address of both the server and the client.
4. Data Link layer: Responsible for collecting the IP packets from Network Layer and prepares it for transmitting over the internet.
   1. Encapsulation: Every packet is given a header and a trailer which consists the Mac addresses for both the client and server and the error check protocols respectively, called as frames.
   2. Sending the frame: Each frame is then sent either using Ethernet cables or wifi signals to the network of devices over the internet.
   3. Recieving the frame: The network device when matched with the frames destination IP it recieves the header and the trailer of the IP packet and processes the IP data packet via correct gateway and routing.
5. Physical Layer: This is layer is responsible for the transmission of data in the physical infrastructure.
   
**Practical example**:

Scenario:

1. Computer A (client) wants to access a website hosted on Computer B (server) through the internet.

Process:

1. Client A opens a web browser and types in the URL of the desired website.
2. The browser creates an HTTP request at the Application Layer, specifying what it wants.
3. This request is passed to the Transport Layer, where TCP breaks it into manageable segments, adds sequence numbers, and other control information.
4. The segmented data is handed to the Network Layer, where IP adds source and destination IP addresses, creating packets.
5. Now, at the Data Link Layer, these packets are encapsulated into frames with MAC addresses added.
6. The frames are then sent through the physical medium (Ethernet cable, Wi-Fi signal, etc.) at the Physical Layer.
7. Along the way, routers at the Network Layer read the destination IP address, decide the best path, and forward the frames accordingly.
8. The frames eventually reach Computer B.
9. Computer B's network interface card (NIC) at the Physical Layer receives the frames, checks the MAC address to see if it matches its own.
10. If the MAC address matches, the frame is passed up to the Data Link Layer where the IP packet is extracted.
11. The IP packet is then passed up to the Network Layer, where the IP address is checked to ensure it's meant for Computer B.
12. Finally, the HTTP request arrives at the Application Layer on Computer B, where the web server software processes it.
13. The web server then generates an HTTP response, which goes through a similar process but in reverse.
14. The response travels back through the layers, from Computer B to Computer A, delivering the requested web page.