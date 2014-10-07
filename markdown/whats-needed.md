# What do we need
for highly available OpenStack clouds?


Let's start
# simple

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
