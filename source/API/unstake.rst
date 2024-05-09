Release the pledge
====================
Description
-----------------
If you don't want to be a validator or staker again, you can use the transaction to release your pledge.

Transaction Format
-------------------
.. code-block::

    {
          from: the address  is validator or staker
          to: release the amount pledged validator
          value: the number of ERB you release
          data:{
               erbie:{
                  type:4
                  version:"0.0.1"
               }
          }
    }

.. csv-table::
    :header: "Parameter", "Datatype", "Description"
    :widths: 10, 10, 30

    "from", "String(hexadecimal) ", "the address  is validator or staker"
    "to", "String(hexadecimal) ", "release the amount pledged validator"
    "value", "String", "the number of ERB you release, format is a hexadecimal string"
    "type", "Int", "Transaction type, value: 4"
    "version", "String", "Version"

Examples
------------------------------
.. code-block::

        data part:

            erbie:{"type":4,"version":"v0.0.1"}

        transaction:
            Convert the above data part to a hexadecimal string and put it in the data section

            curl -X POST -H 'Content-Type: application/json' --data'{"jsonrpc":"2.0","method":"eth_sendTransaction",
            "params": [{"from": "0x94aB2dAA7BBc5A8f62C27D6F8aB87B0e88fE3c48","to": "0x0D53B1035c840030B00dafb216a21E16Bf668895", "value":"0x8ac7230489e80000",
            "data":"0x65726269653a7b2274797065223a342c2276657273696f6e223a2276302e302e31227d"}],
            "id":20211209}' 127.0.0.1:8545
