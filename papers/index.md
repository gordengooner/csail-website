Papers
======

Consistent hashing
------------------

[Consistent Hashing and Random Trees: Distributed Caching Protocols for Relieving Hot Spots on the World Wide Web](http://www.akamai.com/dl/technical_publications/ConsistenHashingandRandomTreesDistributedCachingprotocolsforrelievingHotSpotsontheworldwideweb.pdf), by David Karger et al.

 - handy for uniformly mapping a set of keys to an ever changing set of servers 
   with minimal transfer of keys when new servers are added/removed

  > In this section we define a new hashing technique called consistent hashing. We
  > motivate this technique by reference to a simple scheme for data replication on
  > the Internet. Consider a single server that has a large number of objects that
  > other clients might want to access. It is natural to introduce a layer of caches
  > between the clients and the server in order to reduce the load on the server. In
  > such a scheme, the objects should be distributed across the caches, so that each
  > is responsible for a roughly equal share. In addition, clients need to know
  > which cache to query for a specific object.  The obvious approach is hashing.
  > The server can use a hash function that evenly distributes the objects across
  > the caches. Clients can use the hash function to discover which cache stores a
  > object.  Consider now what happens when the set of active caching machines
  > changes, or when each client is aware of a different set of caches. (Such
  > situations are very plausible on the Internet.) If the distribution was done
  > with a classical hash function (for example, the linear congruential function
  > (ax + b (mod p)), such inconsistencies would be catastrophic. When the range of
  > the hash function (p in the example) changed, almost every item would be ashed
  > to a new location. Suddenly, all cached data is useless because clients are
  > looking for it in a different location.

  > Consistent hashing solves this problem of different “views.” We define a view to
  > be the set of caches of which a particular client is aware. We assume that while
  > views can be inconsistent, they are substantial: each machine is aware of a
  > constant fraction of the currently operating caches. A client uses a consistent
  > hash function to map a object to one of the caches in its view. We analyze and
  > construct hash functions with the following consistency properties.  First,
  > there is a “smoothness” property. When a machine is added to or removed from the
  > set of caches, the expected fraction of objects that must be moved to a new
  > cache is the minimum needed to maintain a balanced load across the caches.
  > Second, over all the client views, the total number of different caches to which
  > a object is assigned is small. We call this property “spread”. Similarly, over
  > all the client views, the number of distinct objects assigned to a particular
  > cache is small. We call this property “load”