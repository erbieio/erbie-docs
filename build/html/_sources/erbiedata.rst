Blockchain Data and Analysis
=====================================
Blockchain explorers are the gateway to the ErbieChain data world. Through blockchain explorers, you can view real-time blocks, transactions, miners, accounts, and other chain-related activities. Read this chapter to understand the data that the block explorer will show you.

ErbieChain is designed to be transparent, and all information is verifiable. Block explorers provide a visual interface for accessing this information, both on ErbieChain's mainnet and testnet.

Data can be divided into basic and aggregate data. Basic data refers to the intuitive data of all activities on the ErbieChain that can be directly obtained from the chain. Aggregate data refers to statistical data aggregated from basic data.

This article only lists basic data.

Basic data
~~~~~~~~~~~~~~~~~~~~~~~
Block
---------------
Every 5 seconds, a new block is added to ErbieChain (unless a block proposer misses their proposal opportunity) so there is a steady stream of data being added to the block explorer. The blocks contain many important pieces of data which you may find useful.

    - Block height – the block number 
    - Timestamp – the time at which the block was proposed
    - Transactions – the number of transactions contained in the block
    - Size – the size of the data in the block (in bytes)
    - Consumed Gas – the total number of gas units consumed by the transactions in the block
    - Gas limit – the total gas limit set by the transactions in the block
    - Other data – any additional data added by Miners to the block
    - Parent hash – the hash of the previous block for the current block
    - Proposer – the Validator selected by algorithm to propose a new block
    - Reward – list of Validators and Stakers who received rewards
    - Delegated account – the delegated account of the Validator who received rewards 
    - Transaction list – a detailed list of all the transactions contained in the block

Transaction
---------------
Blockchain explorers have become a popular way to track the progress of transactions, since you can obtain detailed transaction information to keep track of the progress. Transaction data includes:

    - Transaction hash – the hash generated when the transaction is submitted 
    - Transaction type – identifies the type of ErbieChain and general transactions 
    - Status – indicates if the transaction is pending, failed, or successful 
    - Block height – the block containing the transaction 
    - Timestamp – the time when the miner mined the transaction 
    - Sender – the account address submitting the transaction 
    - Receiver – the recipient address interacting with the transaction or address of the smart contract 
    - Value – the total ERB amount transferred 
    - Transaction fee – the amount paid to the miner for processing the transaction (calculated based on gas prices * used gas)
    - Consumed gas – the actual number of gas units consumed by the transaction 
    - gas price – the price set per gas unit 
    - Seller benefit – seller benefit amount for SNFT transactions 
    - Input data – any extra information required by the transaction

Account
---------------
You can access a lot of data about accounts. It is therefore recommended to use multiple accounts so that your assets and value transfers are not easily tracked. The following is the available data for accounts: 

    - Account address – the public address used to send funds 
    - ERB balance – the amount of ERB associated with the account 
    - Validator delegation – the amount delegated to Validators 
    - Online weight – the online weight value of the Validator 
    - ERB rewards – the ERB rewards received by the Validator 
    - Annual return rate – annual return rate of ERB for the Validator 
    - Transaction history – a list of all transactions where the account was the sender or receiver 
    - Staker delegation – the amount delegated to Stakers 
    - Transaction history – a list of all transactions where the account was the sender or receiver

