**Copyright @ Anshuman Kundu**

# System Design
*by Anshuman Kundu*


#### What is system design?
**Scenario**: A pizza shop with one chef

1. How do you handle more orders?
   You will ask your chef to optmize himself/herself to its efficient best. This is called **Vertical Scaling** which involves optmizing all the processes(here we have only one chef making pizza as the process) to their best capacity to increase throughput.
   
2. How to be **Resilient**?
   If we have only one chef and they fall sick someday, then the shop will not do any business that day. This is called single point of failure and to avoid this we will hire a backup chef and will assign them task only when our master chef is sick or unavailable (Master-Slave) and pay them accordinlgy.

3. How will you grow business more and more?
   Will have to hire more chefs because only one chef cannot handle big business number orders. This is called **Horizontal Scaling**.

4. How will you manager services amongst the chefs?
   Let us say we have two types of incoming orders: one for pizzas and one for garlic bread and we have three chefs in total one with expertise in garlic bread and other two having expertise in Pizzas. So when orders arrive, instead of randomly distributing them to the chefs we should assign Breads to chefs with equivalent expertise and Pizzas to chefs with equivalent expertise. This is will seperate the services inside the shop and will allow the passage of responsibilties within individual services. This is called **Microservice Management**.

5. What are **Distributed systems**?
   When we see our business growing rapidly, it's time for opening of a new shop so that traffic can be distributed. This is called Distributed System.

6. What is Load Balancing?
   So Now we have two shops serving the same set of things. There is a customer and there is a delivery boy as well who delivers the orders to the customers.
   When a customer places an order it reaches to a central team which analyzes which pizza shop the order should be directed according to the minimum total waiting, execution and delivery time. This is called **Load Balancing**.

7. What is Decoupling?
   The delivery boy should not have any relation with the item being delivered, today it's pizza but some other day it can be anything like burger, similary the shop should have no relation with whom they are providing the order to, it can be direct to the customer or to the delivery boy. This makes our business extensive and Seperating the services is called **Decoupling** which always helps in **Extensibility** of our business.

8. What is **Logging and Metrics**?
   Order being placed, executed and delivered, in every stage the logging of the time and metrics keeps track of future proof business.

##### This is a summary of how a system (here pizza shop) is designed and terms used in bold are the attributes of System design. You can replace the chefs with servers who serves reponses when requests come and an analogy can be drawn.


### Horizonatal vs Vertical Scaling: 

You have written some algorithm, some code on your computer which is basically a function which takes some input and provides some output. Now a lot of people saw that piece of code and now want them to use for money. You are ready to do so but you cannot start giving your computer to everyone to use that piece of code. You will expose your code to the internet (Hosting) and through APIs people will request and get their response. 

###### Where will you expose your code?
1. **Self Hosting:** You will set up your own database, configurations and expose your routes and IPs from where people will request and get their responses hence executing that piece of code. But if someone plugs off your computer or there is fault somewhere in electricity and the computer is not responding then because the people needing that code are paying money, you will be in trouble. So it's better to choose cloud based hosting.

2. **Cloud Hosting:** Cloud is basically a set of computers which are kept somewhere with the cloud providers and you sitting far away can put your code their and expose for the people who have paid money can use them. Cloud can manage databases, traffic, configuration, endpoints, faults and lots of other things which will help you focus on your business operations. You can just remote login the cloud system and deploy your code for usage.
   

Now a lot of people are using your code and you are getting paid for the same but the machine you bought on the cloud from the cloud provider is not able to handle a lot of users. Here comes the topic of scaling:

You will make your only single available machine the biggest possible - **Vertical Scaling** or You will buy more small machines - **Horizontal Scaling**.

###### Comparision:

**Vertical Scaling**:
1. No concept of Load Balancing because the operations are to be performed by only one machine. 
2. It will a single point of failure (**Not Resilient**).
3. Communication will be inside a single system i.e **Interprocess communications** which will be fast.
4. Data will not be lost during communication because it's inside a single machine i.e **Consistency**.
5. There will a Limit upto what extent you can make your machine the biggest after that you will have to purchase a new machine i.e **Hardware Limit**.

**Horizontal Scaling**:
1. There will be more than one machine therefore you will have to manage and balance the load of every machine i.e **Load Balancing**.
2. Since there are multiple machines your system will be **Resilient**.
3. Communication will be in the network of machines i.e **Remote process Communication** which will be slow.
4. Data can be lost during communcation because it's in the network and During the comminication between Machine 1 and Machine 2, data can be lost i.e **Inconsistency**.
5. This will scale well as the user count increases.

###### In the real world big systems are built using the hybrid of both of these scaling mechanisms i.e There will a lot of machines but each of them will be having the biggest computation power. This is will make the complete System take good qualities of both mechanisms like Resilience, IPC, Consistency, Good Scaling capability.


### Layers and Protocols:

I opened my Gmail app, typed a message and clicked on send. The application/software allowing me to do so is called **Application Layer**. It allows users to communicate with network devices and servers. This message is then divided into segments with each segment having sequence numbers at the **Transport Layer**.
These segments are then attached with the Source and Destination IP addresses converting them to IP packets at the **Network Layer**. These IP packets are then provided with the Source and Destination MAC addresses at the head of the packet and Error checking message at the tail of the packet converting them to frames at the **DLL Layer**. These frames of messages are then converted into transimission signals so that they can travel to the recipient.
Now these signals reach the Recipient's Physical Layer where it is converted back to frames. These Frames then reach back to the Recipient's DLL layer where frames are checked whether the tail is error free and the head is attached to correct destination address and with this the head and tails are removed leaving the IP packets.
These IP packets reach to the recipient's Network Layer where the IP's are checked and IP attachments are removed leaving them to the segments. These segments then reach to the recipient's Transport layer where sequence wise segments are gathered forming the actual message, if some segment is missing or lost, the error is transmitted back. The complete message is then transferred to the application layer of the recipient where The recipient sees the message in the application of Gmail.   

##### What happens when you enter "google.com"?

