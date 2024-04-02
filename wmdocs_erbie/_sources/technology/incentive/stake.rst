Staking
======================================================================

- The equilibrium of 70,000 ERB stakes exists as a trade-off between network costs, the number of validators, and the total ERB circulation.
- The stake offers economic finality: a quantifiable measure of chain security.

Introduction
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Staking in the ErbieChain protocol requires a Validator to lock at least 70,000 ERBs for a specified period.

ErbieChain operates as a permissionless system, which means that anyone can participate. Such systems need a method to distribute influence among participants. To prevent individuals from creating an excessive number of duplicate identities and overloading the chain, there must be a cost associated with identity creation. In a proof-of-stake system like ErbieChain, participants must stake coins, a limited resource, on the chain.

Roles in Staking
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In the ErbieChain ecosystem, there are two roles related to staking:

1. Validator
2. Staker

Staking Process
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The ErbieChain ecosystem incorporates two staking processes. In essence, these two staking processes represent two distinct roles within the ErbieChain system.

-  Validator
    To become a validator, a user needs to stake at least 70,000 ERBs. Upon block generation, the validator has a chance to earn 0.16 ERB. If the user stakes as a validator but fails to run a node program, no rewards will be given. The larger the stake in ErbieChain, the higher the chance of receiving a reward.

-  Staker
    To obtain the ErbieChain SNFT asset, a user needs to stake a minimum of 700 ERBs. This role doesn't require running a node program. Upon block creation, the staker has an opportunity to earn an SNFT L0 reward. The larger the stake, the higher the likelihood of receiving a reward.

Stake Size
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Each validator in the ErbieChain system must stake at least 70,000 ERB.

This figure is a compromise, small enough to allow wide participation, but sufficiently large to prevent an overload of validators. Essentially, by reducing stakes, we may permit stakeholders to operate more expensive hardware on a higher bandwidth network, increasing the risk of centralization.

Stake Redemption
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Deposits in the ErbieChain are locked for a fixed period, and the redemption time is highly correlated with block occurrences. The specific wait time for each user may vary due to factors like block behavior.

1. Lock-in Period: Users are permitted to initiate redemption transactions after 1,728 blocks, i.e., when the block height at which the staking occurred surpasses 17,280. For instance, if user A stakes at block height 100, the redemption operation can occur after block height 1,738.

    Once the redemption operation is completed, the user no longer receives rewards for participating in consensus.

2. Pre-release Period: After initiating the redemption transaction, the user must wait for another 1,728 blocks before retrieving the original deposit.


