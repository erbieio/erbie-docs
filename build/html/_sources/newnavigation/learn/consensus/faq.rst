Frequently Asked Questions
==========================================

What is Proof of Stake?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Proof of Stake is a class of algorithms that provide security to blockchains by ensuring that valuable assets are lost by attackers engaging in dishonest behavior. Proof of Stake systems require a set of validators to provide some assets, which may be destroyed if the validators engage in some provably dishonest behavior. ErbieChain uses the DRE algorithm + WPoS Proof of Stake mechanism + BFT algorithm to protect the blockchain.

How does Proof of Stake compare to Proof of Work?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Proof of Work and Proof of Stake are both mechanisms for economically suppressing malicious actors from sending spam or defrauding networks. In both cases, nodes that actively participate in consensus "put something into the network," and if they behave badly, they lose that something.

In Proof of Work, that something is energy. The node is called a miner, runs an algorithm designed to calculate a value faster than any other node. The fastest node is entitled to propose a block to the chain. To change the history of the chain or dominate block proposals, a miner must have such powerful computing power that they always win the race. This is very expensive and difficult to execute, which can protect the chain from attack. The energy required to "mine" using Proof of Work is a real-world asset paid by the miner.

Proof of Stake requires nodes (called validators) to explicitly submit cryptographic assets. If validators behave badly, this cryptocurrency may be destroyed because they directly "stake" their assets into the chain, rather than indirectly through energy expenditure.

Proof of Work is more energy-intensive because it consumes electricity during the mining process. On the other hand, Proof of Stake requires very little energy - ErbieChain validators can even run on low-power devices like Raspberry Pis. The Proof of Stake mechanism used by ErbieChain is considered more secure than Proof of Work because the cost of attack is higher and the consequences for attackers are more severe.

What is the Fork Selection Algorithm?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The Fork Selection Algorithm implements the rules for determining which chain is the canonical chain. Ideally, no fork selection rules are needed, because each slot has only one block proposer and one block to choose from. However, occasionally multiple blocks in the same slot or late information can result in multiple choices of block organization near the head of the chain. In these cases, all clients must implement some rules in the same way to ensure that they all choose the correct sequence of blocks. The Fork Selection Algorithm encodes these rules.

ErbieChain chooses the fork with the highest block difficulty value, with a difficulty value of 1 for ordinary blocks and 24 for blackhole blocks.

What is the Finality of Proof of Stake?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The finality of Proof of Stake is the guarantee that a given block is a permanent part of the canonical chain, unless there is a consensus failure or an attacker burns 33% of the total staked ERB. This is the "cryptoeconomic" finality, as opposed to the "probabilistic finality" associated with Proof of Work blockchains. In probabilistic finality, blocks do not have a clear final/non-final state - the longer the time goes by, the less likely it is that a block will be removed from the chain, and users decide for themselves when they have enough confidence that a block is "safe."

Do the rich get richer in Proof of Stake?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ErbieChain weakens the influence of staking on rewards in two ways: the selection of 11 Validators and the reward distribution method. First, the DRE algorithm introduces the concept of distance when selecting 11 Validators. Each time a new block is produced, a landing point is calculated based on the hash of the previous block, and only the 11 miners whose addresses are closest to this landing point will be selected. The staked amount will affect this distance, and staking more can relatively shorten this distance. In addition, for each new block produced, rewards are given to 7 of the 11 Validators, not just the block proposer. The 7 are selected as the earliest 7 Validators to participate in consensus and send messages, avoiding the risk of centralization that comes with using a PoS algorithm.

----

.. [#f1] Some of the content in this document is quoted from `Ethereum <https://ethereum.org/zh/developers/docs/consensus-mechanisms/pos/faqs/>`_ .


