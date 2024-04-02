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
        Nft      *types.AccountNFT         `rlp:"nil"`  //SNFT information
        Staker   *types.AccountStaker      `rlp:"nil"`
        Extra    []byte
    }

In addition to the shared first four data information, the following information is mainly saved:

1. Account extended information
2. SNFT information
3. Validators
4. Stakers
5. SNFT mint sequence number
6. Selected SNFT phase information
7. SNFT information for participating in the competition

Each leaf node does not contain all of the above data, but only stores some of the information based on the account type.

Account Extension Information
---------------------------------------------

.. code-block:: go

    type WormholesExtension struct {
        PledgedBalance     *big.Int         //Validator pledged amount
        PledgedBlockNumber *big.Int         //Validator pledged height
        ExchangerFlag      bool             //Whether it is a Staker
        BlockNumber        *big.Int         //Staker pledged height
        ExchangerBalance   *big.Int         //Staker pledged amount
        SNFTAgentRecipient common.Address   //When receiving SNFT rewards, the owner of SNFT
        VoteBlockNumber    *big.Int         //Block height of the last successful competition for SNFT Creator
        VoteWeight         *big.Int         //Value owned
        Coefficient        uint8            //Node online weight
        // The ratio that exchanger get.
        FeeRate       uint16                //Exchange rate
        ExchangerName string                //Exchange name
        ExchangerURL  string                //Exchange website
        // ApproveAddress have the right to handle all nfts of the account
        ApproveAddressList []common.Address //Authorized address list
        SNFTNoMerge bool                    //Whether it is not an automatic merge flag
    }

SNFT Information
-----------------------------------------------
.. code-block:: go

    type AccountNFT struct {
        Name   string                              //SNFT name
        Symbol string                              //SNFT abbreviation
        Owner                 common.Address       //SNFT owner
        SNFTRecipient         common.Address       //Staker when receiving SNFT rewards
        NFTApproveAddressList common.Address       //SNFT authorized person
        // MergeLevel is the level of NFT merged
        MergeLevel  uint8                          //SNFT merge level
        MergeNumber uint32                         //Number of fragments of SNFT synthesis
        Creator   common.Address                   //Creator of SNFT
        Royalty   uint16                           //SNFT royalty
        Exchanger common.Address                   //Exchange at the time of SNFT casting
        MetaURL   string                           //Location of SNFT metadata
    }

Other Information
---------------------------------------------------
Information on Validators, Stakers, SNFT mint sequence number, selected SNFT phase information, and SNFT information for participating in the competition are all defined in the AccountStaker structure as follows:

.. code-block:: go

    type AccountStaker struct {
        Mint       MintDeep                             //SNFT mint sequence number
        Validators ValidatorList                        //Validators list pledged by the entire network
        Stakers    StakerList                           //Stakers list pledged by the whole network
        Snfts      InjectedOfficialNFTList              //Selected SNFT phase information
        Nominee    *NominatedOfficialNFT `rlp:"nil"`    //SNFT information for participating in the competition
    }

SNFT Storage Introduction
-----------------------------------------------
On the ErbieChain, SNFT contains four levels: MergeLevel mentioned above, SNFT fragments - level 0, 16 SNFT fragments can be combined to form SNFT- level 1, 16 SNFT can be combined to form SNFT collection- level 2, and 16 SNFT collections can be combined to form SNFT period - level 3. Each existing SNFT, regardless of its level, is stored in the leaf node of the tree. After each synthesis from a lower level to a higher level, only the leaf node with the smallest address is kept as the synthesis leaf node, and the information on the other 15 leaf nodes will be deleted.