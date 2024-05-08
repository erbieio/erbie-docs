==========================================
ErbieChain Transactions
==========================================
Generally speaking, blockchain systems have two types of transactions: regular transactions and contract transactions. ErbieChain has made extensions on this basis, including SNFT transfer/exchange, ERB staking, and other transactions.


Staking ERB
==========================================
Description
------------------------------
Users can use this transaction to stake ERB when they want to become validators or stakers. They can also delegate their stakes to other accounts. The gas fee is around 70000.

Transaction Format
------------------------------
.. code-block::     

    {
      from: Staking ERB account address
      to: The staked account address
      value: Staked amount
      data:{
        erbie:{
            type:9
            proxy_address: The SNFT beneficiary
            fee_rate: Staker Fee
            name: Staker Name
            url: Staker URL
            version:"0.0.1"
        }
      }
    }

.. csv-table:: 
    :header: "Parameter", "Datatype", "Description"
    :widths: 10, 10, 30

    "from", "String(hexadecimal) ", "Staking ERB account address"
    "to", "String(hexadecimal) ", "The staked account address."
    "value","String(hexadecimal) ","Staked amount"
    "type", "Int", "Transaction type, value: 9"
    "proxy_address", "String(hexadecimal) ", "The SNFT beneficiary.Optional"
    "fee_rate", "Int", "Staker Fee. value: 1~1000"
    "name", "String", "Staker Name."
    "url", "String", "Staker URL."
    "version", "String", "Version"

Example
------------------------------

.. code-block:: 

    erbie:{"type":9,"version":"v0.0.1","proxy_address":"0x23D85D9B6b366b7670b71049D438b0d88A4e0ca0","fee_rate":1000}
    curl -X POST -H 'Content-Type: application/json' --data
    '{"jsonrpc":"2.0","method":"eth_sendTransaction",
    "params": [{"from": "0x591813F0D13CE48f0E29081200a96565f466B212",
    "to": "0x591813F0D13CE48f0E29081200a96565f466B212",
    "value":"0x8ac7230489e80000",
    "data": "0x776f726d686f6c65733a7b2274797065223a392c2276657273696f6e223a2276302e302
    e31227d"}],"id":51888}' 127.0.0.1:8561

Redeeming ERB
==========================================
Description
------------------------------
Users can use this transaction to redeem their staked ERB. The gas fee is around 50000.

Transaction Format
------------------------------
.. code-block::

    {
      from: Staking ERB account address
      to: Staking ERB account address
      value: Amount to redeem
      data:{
          erbie:{
              type:10
              version:"0.0.1"
          }
      }
    }

.. csv-table:: 
    :header: "Parameter", "Datatype", "Description"
    :widths: 10, 10, 30

    "from", "String(hexadecimal) ", "Staking ERB account address"
    "to", "String(hexadecimal) ", "Staking ERB account address"
    "value","String(hexadecimal) ","Amount to redeem"
    "type", "Int", "Transaction type, value: 10"
    "version", "String", "Version"

Example
------------------------------

.. code-block::

    erbie:{"type":10,"version":"v0.0.1"}
    curl -X POST -H 'Content-Type: application/json' --data
    '{"jsonrpc":"2.0","method":"eth_sendTransaction",
    "params": [{
    "from": "0x591813F0D13CE48f0E29081200a96565f466B212",
    "to": "0x591813F0D13CE48f0E29081200a96565f466B212",
    "value":"0x8ac7230489e80000",
    "data":
    "0x776f726d686f6c65733a7b2274797065223a31302c2276657273696f6e223a2276302e302
    e31227d"}],"id":51888}' 127.0.0.1:8561

Validator Delegation
==========================================
Description
------------------------------
Validators can use this transaction to delegate their responsibilities to a proxy account. The gas fee is around 70000.

Transaction Format
------------------------------
.. code-block::

    {
      from:Validator user address
      to:Validator user address
      data:{
          erbie:{
              type:31,
              proxy_address: Proxy address
              proxy_sign: Proxy address signature
              version:"0.0.1"
          }
      }
    }

.. csv-table:: 
    :header: "Parameter", "Datatype", "Description"
    :widths: 10, 10, 30

    "from", "String(hexadecimal) ", "Validator user address"
    "to", "String(hexadecimal) ", "Validator user address"
    "type", "Int", "Transaction type, value: 31"
    "proxy_address", "String(hexadecimal) ", "Proxy address"
    "proxy_sign", "String(hexadecimal) ", "Proxy address signature"
    "version", "String", "Version"

Example
------------------------------

.. code-block::

    erbie:{"type":31,"version":"v0.0.1","proxy_address":"0x23D85D9B6b366b7670b71049D438b0d88A4e0ca0","proxy_sign":"0x006e19f800d2b097892662b7aa9a8af211cfc754d06a17ced72c9ae5766076902ea817bfa33271cdefba01f5a7247f2e0885f8fab78b6fbf42cbe62f600cf5651b"}
    curl -X POST -H 'Content-Type: application/json' --data
    '{"jsonrpc":"2.0","method":"eth_sendTransaction",
    "params":
    [{"from": "0x591813F0D13CE48f0E29081200a96565f466B212",
    "to": "0x591813F0D13CE48f0E29081200a96565f466B212",
    "data": "0x776f726d686f6c65733a7b2274797065223a392c2276657273696f6e223a2276302e30
    2e31227d"}],
    "id":51888}' 127.0.0.1:8561

Restoring Weight
============================================
Description
------------------------------
Validators can use this transaction to restore their weight when it falls below 70%. The gas fee is around 70000.

Transaction Format
------------------------------
.. code-block::

    {
      from: Validator user address
      to: Validator user address
      data:{
          erbie:{
              type:26,
              version:"0.0.1"
          }
      }
    }

.. csv-table:: 
    :header: "Parameter", "Datatype", "Description"
    :widths: 10, 10, 30

    "from", "String(hexadecimal) ", "Validator user address"
    "to", "String(hexadecimal) ", "Validator user address"
    "type", "Int", "Transaction type, value: 26"
    "version", "String", "Version"

Example
------------------------------

.. code-block::

    erbie:{"type": 26, "version": "v0.0.1"}
    curl -X POST -H 'Content-Type: application/json' --data
    '{"jsonrpc":"2.0","method":"eth_sendTransaction",
    "params": [{
    "from": "0x591813F0D13CE48f0E29081200a96565f466B212",
    "to": "0x591813F0D13CE48f0E29081200a96565f466B212",
    "data": "776f726d686f6c65733a7b2274797065223a2032362c202276657273696f6e223a202276302e302e31227d"}],
    "id":51888}' 127.0.0.1:8561