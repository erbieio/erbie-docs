Weighted Proof of Stake (WPoS)
============================================================

Weighted Proof of Stake (WPoS) is the underlying mechanism supporting the ErbieChain consensus mechanism.

What is Weighted Proof of Stake (WPoS)?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
WPoS is a type of Proof of Stake (PoS) mechanism tailored to the ErbieChain, primarily designed for participating in the consensus of ErbieChain blackhole blocks. Its main feature is that in addition to the amount of staked tokens affecting the stake, the concept of online weight is introduced, which also affects the miner’s own stake. If a node goes offline, its online weight will decrease, reducing its influence on the entire chain, and going online will increase its online weight.

Validators
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To participate in network maintenance and receive block rewards as a validator, users must stake at least 70,000 ERB, and their address will be stored in the world state tree in the backend and sorted by staked token amount and weight.

When a black hole block needs to be created, all validators will initiate a message agreeing to propose a black hole block at a certain height. The proposer of the black hole block will collect messages from the entire network. When the stake of the collected messages is greater than 50% of the entire network, a black hole block will be proposed and broadcasted, and other nodes will verify the block. If it is valid, the block will be added to the ErbieChain.

How to Execute Transactions in ErbieChain Proof of Stake?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The following provides an end-to-end explanation of how to execute transactions in ErbieChain proof of stake WPoS.

1. Nodes stake a portion of their tokens as collateral to gain block generation power and consensus voting rights. The more tokens they stake, the greater weight they have.
2. The ErbieChain system calculates the weight of each node based on the total number of staked tokens and online weight and determines their probability of generating blocks and voting impact. The larger the weight of a node, the greater its chance of generating blocks and its voting power.
3. When a black hole block needs to be produced, the block producer will propose the block according to the voting weight calculated in the previous step, starting with the highest weight. Only if the first few nodes have not proposed a block within the designated time or the block has not been successfully inserted into the canonical chain, the subsequent nodes will have the right to propose a block.
4. All nodes will verify and vote on the block after receiving it. Based on their verification results, each node will choose to adopt or discard the block.

Finality
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
In distributed networks, “finality” refers to the fact that a transaction cannot be changed once it is part of a block. In ErbieChain proof of stake, “state finality points” are used to manage finality. When a block conforms to a state finality point, all the blocks before the block become irreversible, and all historical transactions are therefore immutable.

Security of Cryptoeconomics
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Validators are expected to maintain sufficient hardware and connections to participate in block validation and proposal. In return, validators receive ERB (their staked balance increases). On the other hand, as a validator participating, new channels are opened up for users to attack the network for personal gain or to sabotage. To prevent this, if a validator fails to participate when called upon, they will miss out on ERB rewards; if they engage in dishonest behavior, their existing staked tokens may be destroyed. There are two main behaviors considered to be dishonest: proposing multiple blocks (ambiguous) and submitting conflicting attestations.

Fork Selection
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
When the network operates with integrity at its best, there is always only one new block in the blockchain head and all validators will attest to it. However, due to network delays or multiple block proposers proposing blocks simultaneously (ambiguously), validators may see different views of the blockchain head. Therefore, the consensus client needs an algorithm to determine which block to support. ErbieChain currently follows the chain with the sum of block difficulty values as the main chain, with regular block difficulty values at 1 and black hole block difficulty values at 24.

Proof of stake and security
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Just like in proof of work, there is still a 51% attack threat in proof of stake, but the risk is greater for attackers. Attackers need to obtain 51% of the staked ERB. Then they can ensure that their preferred fork has the most accumulated attestations through their own attestations. The consensus client uses the “weight” of accumulated attestations to determine the correct chain, so attackers can make their fork the canonical chain. However, the advantage of proof of stake compared to proof of work is that the community can launch flexible counterattacks. For example, honest validators can decide to continue building on a non-mainstream chain and ignore the attacker’s fork, while encouraging applications and pools to do the same. They can also decide to forcibly remove the attacker from the network and destroy the ERB they staked. These are strong economic defenses against a 51% attack.

51% attack is just one type of malicious behavior. Bad actors may attempt long-range attacks (although ultimately determinism mitigates that attack vector), short-range “reorganizations” (although proposer weights and attestation periods can mitigate this situation), bounce attacks and equilibrium attacks (which can also be mitigated by proposer weights and these attacks can only be demonstrated under ideal network conditions) or avalanche attacks (which can be counteracted by fork selection algorithms that only consider the latest information).

Overall, proof of stake implemented by ErbieChain is proven to be more economically secure than proof of work.
