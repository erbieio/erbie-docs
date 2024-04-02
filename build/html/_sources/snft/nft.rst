ChainLayer NFT Overview 
========================================================
ErbieChain NFTs aim to provide more reliable and secure decentralized network services for your digital assets.

What are ErbieChain ChainLayer NFTs?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
NFTs are a non-replaceable digital asset that uses blockchain technology for verification and storage and are stored in a distributed network in an encrypted manner. Unlike traditional digital assets, NFTs have uniqueness in ownership, identity, and value.

ErbieChain NFTs are similar to the traditional NFT concept based on the smart contract layer, retaining the characteristics of NFT being indivisible, unique, traceable, and tradable. The difference is that the underlying layer of ErbieChain has implemented the NFT-related 721 standard; that is, ErbieChain directly possesses the functionality related to NFTs.

Therefore, ErbieChain provides "ChainLayer" NFTs, allowing users to directly mint, transfer, and trade NFTs on the chain.

Differences between ChainLayer NFTs and Traditional NFTs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Due to the underlying logic technology implementation of ChainLayer NFTs, the ChainLayer NFTs system has the following unique advantages:

- Minting Quantity: Unlimited.
- Gas Fee: The middle process of the smart contract is omitted in the minting process, so the gas fee is greatly reduced.
- Security: NFTs coexists with the chain and have multi-layer encryption, making them more reliable and secure.

Implementation Details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The NFT information has been extended in the account data structure (refer to the "SNFT Information" section in the ":ref:`Merkle Patricia Trie`" document); that is, the NFT and account amount both exist in the data state tree. Each NFT has a uniquely corresponding NFT address, which is similar to the account address, is 20 bytes long, and is used to identify the NFT. ErbieChain has defined a new data structure in the sent transaction data to support NFT transactions.

.. code-block:: go

    type Wormholes struct {
        Type          uint8            `json:"type"`                        //Transaction type for the added business
        NFTAddress    string           `json:"nft_address,omitempty"`       //NFT address
        ProxyAddress  string           `json:"proxy_address,omitempty"`     //Proxy address
        ProxySign     string           `json:"proxy_sign,omitempty"`        //Signature authorizing the proxy address
        Exchanger     string           `json:"exchanger,omitempty"`         //Exchange address
        Royalty       uint16           `json:"royalty,omitempty"`           //Royalty
        MetaURL       string           `json:"meta_url,omitempty"`          //Location of NFT or SNFT metadata 
        FeeRate       uint16           `json:"fee_rate,omitempty"`          //Exchange fee
        Name          string           `json:"name,omitempty"`              //NFT name
        Url           string           `json:"url,omitempty"`               //Exchange address
        Dir           string           `json:"dir,omitempty"`               //Location of the metadata for this issue of SNFTs
        StartIndex    string           `json:"start_index,omitempty"`       //Start index for this issue of SNFTs
        Number        uint64           `json:"number,omitempty"`            //Data volume of this issue of SNFTs
        Buyer         Payload          `json:"buyer,omitempty"`             //NFT buyer
        Seller1       Payload          `json:"seller1,omitempty"`           //NFT seller1
        Seller2       MintSellPayload  `json:"seller2,omitempty"`           //NFT seller2
        ExchangerAuth ExchangerPayload `json:"exchanger_auth,omitempty"`    //Authorization for the proxy exchange
        Creator       string           `json:"creator,omitempty"`           //NFT creator
        Version       string           `json:"version,omitempty"`           //Version number
        RewardFlag    uint8            `json:"reward_flag,omitempty"`       //Reserved field
        BuyerAuth     TraderPayload    `json:"buyer_auth,omitempty"`        //Buyer authorization
        SellerAuth    TraderPayload    `json:"seller_auth,omitempty"`       //Seller authorization
        NoAutoMerge   bool             `json:"no_automerge,omitempty"`      //SNFT no auto-merge flag
    }


NFT Features
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ErbieChain provides related NFT features, including minting of proprietary NFTs, AI drawings NFT, etc.

- Minting Proprietary NFTs: Users can mint their own NFTs on-chain through their own NFT links.
- AI NFT: Users can get AI-converted ErbieChain NFTs by inputting prompt words.

Minting Methods
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- Calling Interface: Initiate an :ref:`NFT Minting` transaction to ErbieChain.
- Limino Wallet: In the `Limino Wallet <https://www.limino.com/>`_ front-end interface, use the NFT link to mint.