# Open issues
Note: We still had a few issues related to HA in Icehouse. Some of
these are fixed in the pending Juno release.


HA for
## Neutron L3 agents
Note: The Neutron L3 agent has been an issue for some time.


## Active/Passive HA
Note: We were always able to put the L3 agent under active/passive HA
management. That doesn't solve the scaling issue for incoming and
outgoing network traffic though, making the L3 agent a potential
bottleneck.


## Active/Active HA


## `neutron-scheduler`
Note: since Grizzly, we've had the `neutron-scheduler` service
(formerly `quantum-scheduler`). This allows us to assign virtual
routers to L3 agents in a round-robin fashion, such that we can
distribute routers across multiple network nodes. However, this
assignment is permanent and there is no automatic failure detection
for L3 agents. In other words, if an L3 agent goes down, then the
routers don't automatically get reassigned to a new one, and until an
admin intervenes, the corresponding virtual networks have no outside
connectivity, and no metadata proxy services.


## `neutron-ha-tool.py`
Note: `neutron-ha-tool.py` can be integrated with a Pacemaker cluster
to do automatic failover of routers when the L3 agent itself fails
over. This is the approach integrated with SUSE Cloud 3.


## Juno: HA virtual routers
VRRP & DVR *(experimental)*


Highly available
## Nova guests
Still waiting...
