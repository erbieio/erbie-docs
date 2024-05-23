Overview
==============

On the erbie chain, the deployment of smart contracts needs to be written in Solidity language. After deployment, the contract will generate an account that contains two addresses:
**one is address encoded with base58** and begins with the number 1, which is used for interaction with the erbie chain.
**the other one is a 34 byte hexadecimal address**, which is only used for interacting with smart contracts , like a regular wallet account, it has a balance and transaction actions, the difference is that the account of the smart contract itself cannot be controlled by anyone, and all its actions (including transactions) can only be controlled by codes.

  - **TIP**

  - TTOS main network coin transactions use the TTOS address by base58.

  - The address parameters filled in during contract transactions need to use the hexadecimal EVM address.

Introduction to Smart Contracts
----------------------------------

A smart contract is a computer protocol intended to digitally facilitate, verify, or enforce the negotiation or performance of a contract. Smart contracts allow trusted transactions and agreements to be performed among disparate, anonymous parties without the need for a central authority. The purpose of smart contracts is to provide better security methods that is superior to traditional contracts and reduce other transaction costs related to contracts.

Features of Smart Contract
------------------------------

**Formalism**: Smart contracts are based on computer code that minimizes language ambiguity and presents a tight logical structure. The content and execution process are transparent and visible to all nodes, which can observe, record, and verify the contract status through a user interface.

**Irreversibility**: Once the conditions are met, the contract will automatically execute the expected plan. Under the given fact input, the smart contract will inevitably output the correct results and be visualized in the display horizon.

**Non-Fungibility**: The transaction information on the blockchain is open and transparent. Each node can trace the transaction process recorded on the blockchain,making the probability of default is extremely low.

**Anonymity**: According to the cryptography principle of asymmetric encryption, zero-knowledge proof, ring signature, and blind signature, transactions on the blockchain are public, but the transaction parties are anonymous.

Advantages of Smart Contracts
---------------------------------

**First of all, it removed the intermediary.**

Allow users to establish contracts independently based on technology.

**Second, transparency and fairness.**

The Smart Contract use code to write the conditions clearly and record them on the blockchain. The whole process is executed by the program, and even the developer who wrote the code cannot tamper with it.

**Third, flexibility.**

Smart contracts allows users to establish contracts freely, even with strangers globally. In general, smart contracts are one of the core technologies of blockchain, not only playing an executive role in blockchain but also but also expanding the usage scenarios of the blockchain. Because of it`s existence, the blockchain has a broader stage.

Smart contract in erbie chain
-------------------------------------------

The smart contract language used by erbie chain is Solidity which is an object-oriented high-level programming language. The EVM adopted by Transformers supports most of the features of the Solidity standard, and has supported ERC-20, ERC-721, ERC-3525 and other contract standards. Compared with Ethereum, the implementation cost of Transformers contract is lower and the on-chain speed is faster. Other features have been adjusted due to the Transformers’s architecture model.

The specific differences are as follows:

The basic unit of transfer for TTOS currency in the contract is $1^-8TTOS.
For example, there are a total of 999.92064300 TTOS, or 99,992,064,300 contract transfer units.

.. code-block:: go

    >Balance: 999.92064300

- The contract does not support block variables and tx variables.

- The balance attribute value of the address type variable is for reference only and is not recommended for use.

- The type(X) expression only provides limited support and is not recommended for use.

- Prohibit depositing TTOS coins into contracts during contract deployment.

  - **TIPS:**
    Special options and requirements for executing smart contracts on the erbie chain:

  - The gas fee for smart contracts does not require pre input, but if the balance is insufficient to pay for the gas fee, contract execution fails.

  - You can pay a tip to the contract deployer while executing the contract, and the tip amount should not be less than the gas fee.

Preparation before writing contracts
-----------------------------------------

If you are not familiar with Solidity, you can refer to the following link to complete the study of Solidity:

  - `Solidity document <https://docs.soliditylang.org/en/latest/>`_

  - `EVM operation code <https://ethervm.io/>`_

  - `Solidity Writing examples <https://solidity-by-example.org/>`_

The deployment of smart contracts requires the contract source code to be compiled into EVM bytecode, so you should be familiar with the relevant tools for Solidity compilation. The following are the familiar Remix IDE tools that can compile Solidity online:

  - `Remix <https://remix.ethereum.org/>`_

  - `Remix document <https://remix-ide.readthedocs.io/en/latest/>`_

erbie adopts the same standards as Ethereum smart contracts for Ethereum compatible smart contracts. Please read and learn EIP related standards (such as ERC-20) first, and refer to relevant implementation examples to write your own contract.

The reference link is as follows:


  - `EIP <https://github.com/ethereum/EIPs/tree/master/EIPS>`_

  - `ERC <https://eips.ethereum.org/erc>`_

  - `OpenZeppelin <https://github.com/OpenZeppelin/openzeppelin-contracts/tree/master/contracts/token>`_


