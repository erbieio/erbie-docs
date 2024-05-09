Transfer CSBT
===============
Description
-----------------
Creators of csbt can transfer csbt to others, but others can't transfer csbts. That means csbts just can be transfered once

Transaction Format
-------------------
.. code-block::

    {
          from:The sending address of the transaction, which is the creator of csbt.
          to: the address is the new owner of csbt.
          data:{
               erbie:{
                  type:1
                  csbt_address: this is address of csbt
                  version:"0.0.1"
               }
          }
    }

.. csv-table::
    :header: "Parameter", "Datatype", "Description"
    :widths: 10, 10, 30

    "from", "String(hexadecimal) ", "the address is the creator of csbt"
    "to", "String(hexadecimal) ", "the address is the new owner of csbt"
    "type", "Int", "Transaction type, value: 1"
    "csbt_address", "String", "csbt address, example:0x8000000000000000000000000000000000000001"
    "version", "String", "Version"

Examples
------------------------------
.. code-block::

    data part:

        erbie:{"type":1,"csbt_address":"0x8000000000000000000000000000000000000001","version":"v0.0.1"}

    transaction:
        Convert the above data part to a hexadecimal string and put it in the data section

        curl -X POST -H 'Content-Type: application/json' --data'{"jsonrpc":"2.0","method":"eth_sendTransaction",
        "params": [{"from": "0x0D53B1035c840030B00dafb216a21E16Bf668895","to": "0x84EC5C1611f17759a997e303bEF45ee00c3647Cc",
        "data":"0x65726269653a7b2274797065223a312c22637362745f61646472657373223a22307838303030303030303030303030303030303030303030303030303030303030303030303030303031222c2276657273696f6e223a2276302e302e31227d"}],
        "id":20211209}' 127.0.0.1:8545

