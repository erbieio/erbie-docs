Merkle Patricia Trie
===================================================

The Merkle Patricia Trie provides a structure for storing all (key, value) pairs and is authenticated through encryption.

The Merkle Patricia Trie is fully deterministic, which means that the trie with the same (key, value) pairs will always be identical, even down to the last byte. This means that they have the same root hash, making insertion, retrieval, and deletion operations have an unbeatable O(log(n)) efficiency. In addition, compared to more complex comparison-based dictionary trees like red-black trees, the Merkle Patricia Trie is easier to understand and code.

Application of Merkle Patricia Trie in ErbieChain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Multiple types of information are stored in the leaf nodes, and the overall data structure is as follows:

.. code-block:: go

    type Account struct {
        Nonce    uint64                                 //Transaction serial number
        Balance  *big.Int                               //Account balance
        Root     common.Hash                            //Merkle root of the trie
        CodeHash []byte                                 //Hash of the contract code
        Worm     *types.WormholesExtension `rlp:"nil"`  //Account extended information
        Csbt     *types.AccountCSBT        `rlp:"nil"`  //csbt information
        Staker   *types.AccountStaker      `rlp:"nil"`
        Extra    []byte
    }

In addition to the shared first four data information, the following information is mainly saved:

1. Account extended information
2. CSBT information
3. Validators
4. Stakers
5. CSBT mint sequence number

Each leaf node does not contain all of the above data, but only stores some of the information based on the account type.

Account Extension Information
---------------------------------------------

.. code-block:: go

    type WormholesExtension struct {
        PledgedBalance     *big.Int                     //validator's sum pledged balance
        PledgedBlockNumber *big.Int                     //the last blocknumber that staker pledged
        Coefficient        uint8                        //Node online weight
        StakerExtension    StakersExtensionList         //List of validators pledged by staker
        ValidatorExtension ValidatorsExtensionList      //List of STakers pledged to the validator
        ValidatorProxy     common.Address               // proxy address of validator
    }

CSBT Information
-----------------------------------------------
.. code-block:: go

    type AccountCSBT struct {
        Owner   common.Address  //owner of csbt
        Creator common.Address  //creator of csbt
    }

Other Information
---------------------------------------------------
Information on Validators, csbt creators and csbt mint sequence number  are all defined in the AccountStaker structure as follows:

.. code-block:: go

    type AccountStaker struct {
        Mint       MintDeep                             //CSBT mint sequence number
        Validators ValidatorList                        //Validators list pledged by the entire network
        CSBTCreators StakerList                         //creator list who can get csbt first
    }

CSBT Storage Introduction
-----------------------------------------------
On the ErbieChain, each existing CSBT is stored in the leaf node of the tree.