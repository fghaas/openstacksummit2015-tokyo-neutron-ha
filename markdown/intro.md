### Clusters
### Routers
### Agents
and
### Networks
**High Availability in Neutron**

Florian Haas / Assaf Muller / Adam Spiers

[@xahteiwi](https://twitter.com/xahteiwi) / [@assafmuller](https://twitter.com/assafmuller) / [@adamspiers](https://twitter.com/adamspiers)


### Neutron HA
needs a look from
# 3
different angles

Note: *Florian*: It should be obvious that we want and need high
availability for all aspects of OpenStack, to include OpenStack
services, storage, databases, VMs... you name it. Networking in
particular requires us to look at HA from 3 different perspectives.


Neutron
## API service
`neutron-server`

Note: *Florian*: First, there's the API services and associated
plugins.


Neutron
## DHCP servers
dhcp-agent

Note: *Florian*: Then, it's DHCP address assignment and network
configuration on DHCP-enabled subnets, the responsibility of the
Neutron DHCP agent.


Neutron
## Virtual routers
l3-agent

Note: *Florian*: And lastly, HA for virtual routers, which is on the
L3 agent's turf.

And we'd like to do that giving you some insight both into what's
upstream, and what HA features vendors add. And because we can't bring
*every* OpenStack vendor in for this talk, we figured it would be good
to compare two solutions, namely the ones from Red Hat and
SUSE. Apologies to Ubuntu and Mirantis folks in the audience; if you
feel like it, we can do a panel session in Austin. So with that, it's
over to Adam, starting out with HA considerations for
`neutron-server`.