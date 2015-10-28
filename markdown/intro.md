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
Note: It should be obvious that we want and need high availability for
all aspects of OpenStack, to include OpenStack services, storage,
databases, VMs... you name it. Networking in particular requires us to
look at HA from 3 different perspectives.


Neutron
## API service
`neutron-server`
Note: First, there's the API services and associated plugins.


Neutron
## DHCP servers
dhcp-agent
Note: Then, it's DHCP address assignment and network configuration on
DHCP-enabled subnets, the responsibility of the Neutron DHCP agent.


Neutron
## Virtual routers
l3-agent
Note: And lastly, HA for virtual routers, which is on the L3 agent's
turf.