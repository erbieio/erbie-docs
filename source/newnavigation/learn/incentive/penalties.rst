Punishment Mechanisms
==============================

This applies to actions that could potentially be part of a chain attack. In such cases, the validator loses a significant portion of their stake and is expelled from the protocol.

ErbieChain has two punishment mechanisms in place:

1. Stake Penalty: If a validator's node is found to have signed a consensus on two blocks of the same height, the validator's stake is penalized as follows:
   
   .. image:: punishment.png

2. Reduced Online Weight: The online weight is related to the probability of being selected as a consensus participant. If a node is discovered to be offline, the system reduces the online weight of the node. This results in the node being unable to participate in block consensus, and thus it can no longer receive block generation incentives. Users who join the ErbieChain network should pay particular attention to online weights and restore weights promptly if necessary.
   
   .. note::
      Methods for Restoring Weights:
        1. Automatic: A node's successful participation in consensus will automatically restore its weight to 70.
        2. Manual: This can be done first by operating the `wallet <https://www.limino.com/>`_ and then initiating a :ref:`Restoring Weight` transaction.
   .. image:: onlineweight.png

