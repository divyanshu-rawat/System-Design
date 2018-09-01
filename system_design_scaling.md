
System Design Basics: Horizontal vs. Vertical Scaling

Horizontal scaling is adding more machines to deal with increasing requirements. These machines handle requests in parallel to improve user experience. 

Vertical scaling is replacing the current machines with more advanced machines to improve throughput and hence response time. The techniques are used in conjunction in real world systems.


StackOverflow -

Horizontal scaling means that you scale by adding more machines into your pool of resources whereas Vertical scaling means that you scale by adding more power (CPU, RAM) to an existing machine.

An easy way to remember this is to think of a machine on a server rack, we add more machines across the horizontal direction and add more resources to a machine in the vertical direction.

An important advantage of horizontal scalability is that it can provide administrators with the ability to increase capacity on the fly. Another advantage is that in theory, horizontal scalability is only limited by how many entities can be connected successfully. The distributed storage system Cassandra, for example, runs on top of hundreds of commodity nodes spread across different data centers. Because the commodity hardware is scaled out horizontally, Cassandra is fault tolerant and does not have a single point of failure (SPoF).

In a database world horizontal-scaling is often based on the partitioning of the data i.e. each node contains only part of the data, in vertical-scaling the data resides on a single node and scaling is done through multi-core i.e. spreading the load between the CPU and RAM resources of that machine.

With horizontal-scaling it is often easier to scale dynamically by adding more machines into the existing pool - Vertical-scaling is often limited to the capacity of a single machine, scaling beyond that capacity often involves downtime and comes with an upper limit.

Good examples of horizontal scaling are Cassandra, MongoDB, Google Cloud Spanner .. and a good example of vertical scaling is MySQL - Amazon RDS (The cloud version of MySQL). It provides an easy way to scale vertically by switching from small to bigger machines. This process often involves downtime.

Horizontal-scaling through partitioning and vertical-scaling through multi-core support.


Horizontal Scaling - also referred to as "scale-out" is basically the addition of more machines or setting up a cluster or a distributed environment for your software system. This usually requires a load-balancer program which is a middle-ware component in the standard 3 tier client-server architectural model.

Load-Balancer is responsible to distribute user requests (load) among the various back-end systems/machines/nodes in the cluster. Each of these back-end machines run a copy of your software and hence capable of servicing requests. This is just one of the various functions that load balancer may be performing. Another very common responsibility is "health-check" where the load balancer uses the "ping-echo" protocol or exchanges heartbeat messages with all the servers to ensure they are up and running fine.

The request-response can also be done in 2 different ways:

Load Balancer always acts as an intermediary program for every response - In this case, once the request has been handed over to the server by the load balancer, any response from the server to the user will go through the load balancer. So the server machines that are actually servicing the request will never directly interface with the user machine running the client application. The machine hosting the load balancer program will be handling all the requests/responses to and from the user.

Load Balancer does not act as an intermediary for the responses coming from the server machine - In this case, once the server has received the request from load-balancer, it bypasses the load balancer and communicates it responses directly to the client.

Ref -  https://stackoverflow.com/questions/11707879/difference-between-scaling-horizontally-and-vertically-for-databases