# DHCP agents

Note: *Florian*: So with that said about HA considerations for
`neutron-server`, we want to cut over to another component where HA
considerations start geting a little more complex, and that is the
Neutron DHCP agents.


### `dhcp_agents_per_network=N`

Note: *Adam*: introduced to `neutron.conf` in Juno by [gerrit#27907:
Enable network to be scheduled to N DHCP
agents](https://review.openstack.org/#/c/27907/)


<!-- .slide: data-background-image="images/adam/04.svg" data-background-size="contain" -->
Note: *Adam*:


<!-- .slide: data-background-image="images/adam/05.svg" data-background-size="contain" -->
Note: *Adam*: 


<!-- .slide: data-background-image="images/adam/06.svg" data-background-size="contain" -->
Note: *Adam*:


http://docs.openstack.org/admin-guide-cloud/networking_multi-dhcp-agents.html
Note: *Adam*: