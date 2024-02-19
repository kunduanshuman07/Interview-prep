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
   What if there is a power outage in our store? We need to create backups and open another store somewhere else to about single point of failure. This makes the business Fault tolerant and gives quicker response.
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
   -> Increasing the capacity of a single source to handle the load.
   -> Single point of failure
   -> Consistent with data because all data transactions are from one resource only.
   -> There is a hardware limit.
2. Horizontal Scaling: 
   -> Increasing the resource count to handle the load.
   -> Its Resilient.
   -> Inconsistent with data because transactions can be from any resource at any time.
   -> Good Scalability. 
