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


### `agent_scheduler`

    # neutron ext-list
    +-----------------------+-----------------------------+
    | alias                 | name                        |
    +-----------------------+-----------------------------+
    | ...                   | ...                         |
    | l3_agent_scheduler    | L3 Agent Scheduler          |
    | ...                   | ...                         |
    | dhcp_agent_scheduler  | DHCP Agent Scheduler        |
    | ...                   | ...                         |
    +-----------------------+-----------------------------+

Note: since Grizzly, we've had the `agent_scheduler` extension.
In Havana it was split into separate DHCP and L3 agent scheduler
extensions. The latter allows us to assign virtual
routers to L3 agents in a round-robin fashion, such that we can
distribute routers across multiple network nodes. However, this
assignment is permanent and there is no automatic failure detection
for L3 agents. In other words, if an L3 agent goes down, then the
routers don't automatically get reassigned to a new one, and until an
admin intervenes, the corresponding virtual networks have no outside
connectivity, and no metadata proxy services.


## `neutron-ha-tool.py`
(pre-Juno)
Note: `neutron-ha-tool.py` can be integrated with a Pacemaker cluster
to do automatic failover of routers when the L3 agent itself fails
over. This is the approach integrated with SUSE Cloud 3.


## Agent rescheduling
`allow_automatic_l3agent_failover = True`
Note: this automatically reschedules routers associated with an L3
agent that is down. This is extremely slow, however, and likely to
cause user-impacting network downtime.


## HA virtual routers
*(experimental)*
Note: HA virtual routers employ keepalived to maintain a VRRP gateway
address inside a router namespace on two network nodes. Failover is
extremely quick, meaning you do not lose a ping, but HA routers
presently don't replicate connection state, so while the failover is
quick enough to not drop a ping, existing TCP connections *will* die
or need to be recreated. `conntrackd` is a logical addition.


## Distributed virtual routers
*(experimental)*
Note: there are several limitations to DVR and L3 HA in Juno. Most
importantly, right now you can have a router that is *either* DVR *or*
HA (with VRRP), but not both. So for any router, you can fix the SPOF
or the bottleneck, but not both. DVR is also only supported with
VxLAN.
