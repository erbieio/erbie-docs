Gossip
====================================================================
The broadcast domain in ErbieChain includes all information that needs to be rapidly disseminated throughout the entire network. This includes blocks, proofs, authentication, exits, and forfeitures. The maximum limit of broadcast payloads to be received and transmitted depends on various metadata stored locally on each node.

ErbieChain node communication uses the Gossip protocol. 

The Gossip protocol, also known as the Epidemic protocol, is a protocol for information exchange between nodes or processes based on the spread of epidemics. It is widely used in distributed systems, ensuring that all nodes in the network have consistent data.

Types of Gossip protocols
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Gossip protocols can be divided into several types:

- Dissemination protocols or Rumor-mongering protocols:
    
    These protocols work through flood agents in the network, nodes directly forward broadcast data to all neighboring nodes. This approach can improve the network's robustness, but can easily cause broadcast storms.

- Anti-entropy protocols: 

    These are used to repair replicated data, operations are performed by comparing and coordinating differences.

- Protocols that Compute Aggregates: 

    By sampling the information of the nodes in the network and combining these values to obtain a system-wide value, the aggregate value of the network can be calculated.

Gossip Data Transmission
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

There are three interaction modes between two nodes A and B in the Gossip protocol:

1. Push mode: Node B pushes data (key, value, version) and corresponding version number to node A, and node A updates the data in node B that is newer than its own.
2. Pull mode: Node A only pushes data key and version to node B, and node B pushes data (key, value, version) that is newer than node A to node A, and node A updates its own data.
3. Push-Pull mode: Based on the Pull mode, node A pushes its own data that is newer than node B to node B, and node B updates its own data. In other words, after Pull, node A updates the information held by node B based on its own information.
    
In essence, the Push mode involves the initiating node sending its information to another node. The Pull mode involves the initiating node retrieving data from another node. The Push-Pull mode involves the initiating node both sending and retrieving data, providing a more efficient means of data propagation.