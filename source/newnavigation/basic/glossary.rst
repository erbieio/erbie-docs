Erbie's Glossary
------------------

CSBT
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
CSBT is the secondary native token of the ErbieChain blockchain.

The ErbieChain blockchain automatically mints CSBT, dividing it into 16 equal segments, minting each one separately, and each having a unique identifier on the chain. Each standard block randomly selects four stakers to issue 1 CSBT L0 each as an immediate reward.

ERB
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ERB is the primary cryptocurrency of the ErbieChain blockchain.

It is used to pay for internal transactions, transaction fees in the CSBT marketplace, gas fees, and ongoing storage fees.

Consensus
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The confirmation of the validity of each block is achieved through a voting process involving all validators.

Stake
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Staking involves the immobilization of your ERB assets on the ErbieChain blockchain for a set period. This period of immobilization affords stakers increased privileges on the network.

Validator
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Validators are a crucial component of the ErbieChain network infrastructure. They perform key tasks such as block creation, participation in block and state verification, storage of all blockchain data, transaction processing, and providing services and data to the network. A minimum stake of 70,000 ERB is required to activate validator software.

Staker
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Within the ErbieChain ecosystem, there are two roles: Validators and Stakers. Stakers form an additional incentivized role for earning block rewards on the ErbieChain. To facilitate a multi-tiered ecosystem, users can stake ERB to become stakers and become eligible for block rewards. Each block randomly selects four stakers to distribute CSBT as immediate rewards.

Block
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Blocks refer to a combination of transactions and include the hash of the previous block on the chain, which can generally be divided into the block header and the block body. ErbieChain has a unique field called 'Extra' which extends it, and includes the following fields:

- Validators：11 validators
- Seal：Block proposer's signature on the block
- CommittedSeal：Collection of validator signatures on the block
- ExchangerAddr：4 Staker addresses that receive the CSBT reward
- ValidatorAddr：7 Validator addresses that receive the ERB reward
- RewardSeal：Signature collection of the previous regular block
- EmptyBlockMessages： Blackhole block messages

Blackhole Block
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
In ErbieChain’s consensus mechanism, if the number of selected nodes offline exceeds 5 or more, a blackhole block routine is triggered. ErbieChain transactions can still be processed normally in the blackhole block. After the blackhole block is generated, the ErbieChain program will initiate a punishment mechanism to deduct the weight score of the offline verifiers, which will affect the probability of verifiers being selected to participate in the consensus.
