### Neutron HA
in
## SUSE OpenStack Cloud 5
Note: *Adam*:


### SUSE OpenStack Cloud 5

-   released May 2015
-   based on Juno
-   third release with HA support

Note: *Adam*: SUSE OpenStack Cloud first added HA support to release 3
in May 2014.


### Flexible architecture

-   You choose:
    - how many clusters
    - what goes in each cluster
-   Clusters can be grown over time
Note: *Adam*:


### HAproxy

-   `neutron-server` active/active behind HAproxy<br/>
    (same for most other OpenStack services)
-   One VIP per network per cluster
Note: *Adam*:


### Pacemaker

manages:
-   HAproxy
-   *all* OpenStack services, including:
    -   `neutron-server`
    -   `neutron-{l3,dhcp,openvswitch}-agent`
    -   `neutron-ha-tool`
    -   `neutron-{lbaas,metadata,metering}-agent`
Note: *Adam*:


### DHCP

`/etc/neutron/neutron.conf`

```erb
dhcp_agents_per_network = <%= @network_nodes_count %>
```
Note: *Adam*:


### HA routers

-   `allow_automatic_l3agent_failover = False`
-   Entrust Pacemaker with monitoring / fencing
Note: *Adam*:


### `neutron-ha-tool`
#### Unique solution: custom RA

-   `monitor` action fails if any l3-agents are dead
-   `start` action uses `neutron-ha-tool.py` script
    -   migrates routers away from dead l3-agents
-   `stop` action is a no-op (will never cause fencing)
Note: *Adam*:


## DVR

-   Technical preview in SUSE OpenStack Cloud 5
-   Supported in SUSE OpenStack Cloud 6 (based on liberty)
Note: *Adam*:


### Compute node HA

-   Coming in SUSE OpenStack Cloud 6
-   Pacemaker cluster extended to compute nodes:
    -   manages `neutron-openvswitch-agent`
    -   fences misbehaving compute nodes
Note: *Adam*:
