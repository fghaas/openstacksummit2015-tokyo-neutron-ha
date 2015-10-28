HA for
## Neutron L3 agents
Note: *Florian*: The Neutron L3 agent has been a tricky HA challenge
for just about Neutron's entire existence, up to this point.


<!-- .slide: data-background-image="images/assaf/00.svg" data-background-size="contain" -->
Note: *Assaf*:


<!-- .slide: data-background-image="images/assaf/01.svg" data-background-size="contain" -->
Note: *Assaf*:


<!-- .slide: data-background-image="images/assaf/02.svg" data-background-size="contain" -->
Note: *Assaf*:


<!-- .slide: data-background-image="images/assaf/03.svg" data-background-size="contain" -->
Note: *Assaf*:


<!-- .slide: data-background-image="images/assaf/04.svg" data-background-size="contain" -->
Note: *Assaf*:


<!-- .slide: data-background-image="images/assaf/05.svg" data-background-size="contain" -->
Note: *Assaf*:


<!-- .slide: data-background-image="images/assaf/06.svg" data-background-size="contain" -->
Note: *Assaf*:


<!-- .slide: data-background-image="images/assaf/07.svg" data-background-size="contain" -->
Note: *Assaf*:


<!-- .slide: data-background-image="images/assaf/08.svg" data-background-size="contain" -->
Note: *Assaf*:


Remember
### state visibility?
Update port binding host value whenever agent reports state change
Note: *Assaf*:


Assumes
## control plane
is operational!
Note: *Assaf*:


## No l2pop
Failover assumes data plane connectivity
## L2pop
Failover assumes messaging server, database, target L3 agent and neutron-server
Note: *Assaf*:


## Coming up
in Mitaka
Note: *Assaf*:


### L3 HA & DVR integration
Note: *Assaf*:


`neutron router-update --ha=True <old_router>`
Note: *Assaf*:
