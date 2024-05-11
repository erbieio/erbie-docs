Validator and Staker
=====================
Description
-----------------
You can use the transaction to be a validator or staker.
If you want to be a alidator, you need to stake to yourself. When sending the transaction, you can set porxy adddress if you want.
If users want to be stakers, they need to stake to validators.

Transaction Format
-------------------
.. code-block::

    {
          from: the address  who want to be validator or staker
          to: the address is himself or validator.
          value: The number of ERB you stake
          data:{
               erbie:{
                  type:3
                  proxy_address: this is proxy address of validator
                  version:"0.0.1"
               }
          }
    }

.. csv-table::
    :header: "Parameter", "Datatype", "Description"
    :widths: 10, 10, 30

    "from", "String(hexadecimal) ", "the address  who want to be validator or staker"
    "to", "String(hexadecimal) ", "the address is himself or validator."
    "value", "String", "Staking price, format is a hexadecimal string"
    "type", "Int", "Transaction type, value: 3"
    "proxy_address", "String", "proxy_address, example:0x94aB2dAA7BBc5A8f62C27D6F8aB87B0e88fE3c48 or empty string"
    "version", "String", "Version"

Examples
------------------------------
.. code-block::

    validator example:
        data part:

            erbie:{"type":3,"proxy_address":"0x94aB2dAA7BBc5A8f62C27D6F8aB87B0e88fE3c48","version":"v0.0.1"}

        transaction:
            Convert the above data part to a hexadecimal string and put it in the data section

            curl -X POST -H 'Content-Type: application/json' --data'{"jsonrpc":"2.0","method":"eth_sendTransaction",
            "params": [{"from": "0x0D53B1035c840030B00dafb216a21E16Bf668895","to": "0x0D53B1035c840030B00dafb216a21E16Bf668895", "value":"0x8ac7230489e80000",
            "data":"0x65726269653a7b2274797065223a332c2270726f78795f61646472657373223a22307839346142326441413742426335413866363243323744364638614238374230653838664533633438222c2276657273696f6e223a2276302e302e31227d"}],
            "id":20211209}' 127.0.0.1:8545


    staker example:
        data part:

            erbie:{"type":3,"proxy_address":"","version":"v0.0.1"}

        transaction:
            Convert the above data part to a hexadecimal string and put it in the data section

            curl -X POST -H 'Content-Type: application/json' --data'{"jsonrpc":"2.0","method":"eth_sendTransaction",
            "params": [{"from": "0x94aB2dAA7BBc5A8f62C27D6F8aB87B0e88fE3c48","to": "0x0D53B1035c840030B00dafb216a21E16Bf668895", "value":"0x8ac7230489e80000",
            "data":"0x65726269653a7b2274797065223a332c2270726f78795f61646472657373223a22222c2276657273696f6e223a2276302e302e31227d"}],
            "id":20211209}' 127.0.0.1:8545