# What do we need
for highly available OpenStack clouds?


Let's start
## simple

Note: The absolutely simplest OpenStack deployment is one where you
install all the services onto one node. But that's really only
relevant in lab setups, so let's define our minimum viable OpenStack
deployment thus:


![Simple OpenStack cloud](images/simple-cloud.svg)

Note:
- A single API node, this is where all your client-side API
requests come in. Possibly via the dashboard, possibly directly from a
client.
- A single controller node,
- a handful of compute nodes,
- a network node to enable outside network access to and from your cloud.
Needless to say, such a configuration is chock-full of single points
of failure, and bottlenecks.


Now we want to
## eliminate
SPOFs and bottlenecks.


Ideally, this would lead us to:


![Simple OpenStack cloud](images/ha-cloud.svg)
Note:
- Highly available, load-balanced API nodes, eliminating both a
  bottleneck and a SPOF.
- Highly available controller nodes, eliminating a SPOF.
- Highly available network nodes, eliminating a bottleneck and a SPOF.
- As many compute nodes as we want.


## API nodes
Note:
For API nodes, we want to be able to deploy as many as needed,
preferably load-balanced.


## Controller nodes
Note: For some OpenStack services, we can only ever have one, or at
least only one that is actually hit by client requests at any given
time.


## Compute nodes


## Network nodes
Note: these are the most tricky ones, because active/passive HA almost
never cuts it, and active/active has been tricky, up to and including
Icehouse.


## Infra nodes
Note: ... and then, importantly, we have a couple of services that
need HA and a certain amount of scalability, even though they're only
**used** by OpenStack, rather than being a part of OpenStack
itself. Classic examples would be our MySQL database and our RabbitMQ
nodes.
