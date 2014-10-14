# Conventions
and
# best practices
for OpenStack HA


## Infrastructure


### RDBMS High Availability
MySQL/Galera
Note: SUSE is a notable exception. Their SUSE Cloud product uses
PostgreSQL as the database, relying on DRBD for replication.


### RabbitMQ High Availability
Note: There are multiple ways to do this, including mirrored queues or
HA queues. Generally though, OpenStack services **resend** messages
that get lost, so as long as you're not bottlenecking on your RabbitMQ
throughput it's fine to just keep several instances alive, and use a
cluster manager like Pacemaker to move a VIP around.


## API Endpoint Load Balancing
HAProxy
Note: Again, there's more than one way to do this. Possible
alternatives are DNS round-robin load balancing, or using
`ldirectord`. Most vendor-integrated solutions use HAProxy though.


## HA Service Management
Corosync/Pacemaker


## HA Cluster Storage
Ceph


## Deployment automation
