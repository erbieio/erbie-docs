Consensus
---------------------------

**Consensus mechanisms are commonly referred to as Proof of Stake, Proof of Work, or Proof of Authority protocols. However, these are merely components of a consensus mechanism that guards against Sybil attacks. Consensus mechanisms constitute a system composed of a comprehensive set of ideas, protocols, and incentives. This system enables a network of distributed nodes to reach consensus on the state of the blockchain.**

ErbieChain's consensus mechanism is based on the Dynamic Random Election Algorithm (DRE). This mechanism employs the Byzantine Fault Tolerance (BFT) algorithm for consensus in ordinary blocks and the DRE algorithm to elect validators of the BFT algorithm for consensus. Apart from ordinary blocks, ErbieChain introduces the concept of the ‘blackhole block’ to address scenarios in which there are too many malicious validators of the BFT algorithm, thus inhibiting the production of ordinary blocks. In these instances, the ErbieChain uses the Weighted Proof of Stake (WPoS) consensus algorithm for consensus on these 'blackhole' blocks.

.. toctree::
   :titlesonly:

   intro

.. toctree::
   :titlesonly:

   dre

.. toctree::
   :titlesonly:

   pos

.. toctree::
   :titlesonly:

   bft

.. toctree::
   :titlesonly:

   flow

.. toctree::
   :titlesonly:

   faq

