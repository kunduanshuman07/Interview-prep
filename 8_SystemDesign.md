**Copyright @ Anshuman Kundu**

# Complete System Design with best explanations:


### System:
An architecture or a set of softwares or a set of technologies combined together, which interacts with each others to serve a certain set of users to fulfill a certain set of requirements. 
A system is built considering three factors in mind:
1. Users
2. Requirements of those users
3. Components needed to build the system

#### Real world Systems:
1. Hospitals
2. Theatres
3. Police stations

Components of Real world systems:
1. Walls
2. Floors
3. Ceiling
4. Electrical Supply
5. Water Supply, etc.

#### Computing systems:
1. Instagram
2. Whatsapp
3. Hotstar

Components of Computing systems:
1. Servers
2. Databases
3. Caches
4. Applications
5. Message Queues

### Design
The Process of selecting the components, modules and software technologies to complete the user requirements is called design.

### System Design
###### Designing a System (System Design) -> The process of identifying the problems, pointing out the users and their requirements, efficiently choosing components, modules and software technologies, verifying how those softwares will interact with each other to meet the specific needs of the users and solve the desired problem is called System Design.


### Components of System Design?
1. The core of a system is data which a user can access and manipulate depending upon their needs.
2. Data is stored in Databases.
3. To communicate with databases we have applications in the form of Mobile Apps, Desktop Apps or Web applications.
4. These applications communicate with the databases with the help of communication protocols like HTTP/TCP/IP, etc.
5. In a system one application needs to communicate with other applications which is a software level interaction with the help of APIs.

###### A Basic System Overview: A User tries interacting with a system which in turn is made of applications(servers) and databases connected with networks. Applications interact with each other using APIs and Applications interact with databases using communication protocols like HTTP/TCP/IP. All these applications/servers are basically codes running on some machine and these machines are deployed on large scale servers which are basically cloude providers like AWS, GCP, Azure, etc.
Therefore the 3 most important requirements of a system are databases, servers and network.

#### Client Server Architecture:
1. Interaction between client and the server completely makes the client server architecture.
2. Client is the presentation layer where user requests something from the server which is at the backend performs some or no logical operations on the data being fetched from the database and returns in the form of a response.
3. When majority of the logical computations on the data is done on the client side, it's called a thick client.
4. When majority of the logical computations on the data is done on the server side, it's called a thin client.
5. Usually there is a client and a server. Client is the presentation layer and the server holds the logical computations and the data. This is called a 2-tier architecture. But then sometimes there is data being very heavy and very huge logical computations, in order to split the load, the 2-tier is broken down to 3-tier architecture namely Client-Server-Database. If required a n-tier architecture is also built which basically holds caching, load balancers, proxies, etc which are integrated in between Client-Server-Database to help design more complex systems.
