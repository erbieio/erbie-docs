Network
============
ErbieChain is a peer-to-peer network comprised of thousands of nodes. These nodes need to communicate with each other using standard protocols. The "network layer" is the protocol stack that enables nodes to find each other and exchange messages. These messages can be "broadcast" messages (one-to-many communication) or requests and replies exchanged between specific nodes (one-to-one communication). Each node must follow certain network rules to ensure the correct sending and receiving of messages. These rules include maintaining accurate records of the network topology and online nodes, verifying received messages against the sender’s signature, and propagating broadcast messages to all nodes.

.. toctree::
   :titlesonly:

   p2p

.. toctree::
   :titlesonly:

   gossip

.. toctree::
   :titlesonly:

   synch