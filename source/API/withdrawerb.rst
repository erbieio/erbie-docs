Withdraw ERB
===============
Description
-----------------
Send ERB to owner of csbt. to must be same as the owner of csbt.

Transaction Format
-------------------
.. code-block::

    {
          from: out of ERB's account
          to: the address is the owner of csbt.
          value: the number of ERB you send
          data:{
               erbie:{
                  type:2
                  csbt_address: this is address of csbt
                  version:"0.0.1"
               }
          }
    }

.. csv-table::
    :header: "Parameter", "Datatype", "Description"
    :widths: 10, 10, 30

    "from", "String(hexadecimal) ", "the address is out of ERB's account"
    "to", "String(hexadecimal) ", "the address is the new owner of csbt"
    "value", "String", "The number of ERB you send"
    "type", "Int", "Transaction type, value: 2"
    "csbt_address", "String", "csbt address, example:0x8000000000000000000000000000000000000001"
    "version", "String", "Version"

Examples
------------------------------
.. code-block::

    data part:

        erbie:{"type":2,"csbt_address":"0x8000000000000000000000000000000000000001","version":"v0.0.1"}

    transaction:
        Convert the above data part to a hexadecimal string and put it in the data section

        curl -X POST -H 'Content-Type: application/json' --data'{"jsonrpc":"2.0","method":"eth_sendTransaction",
        "params": [{"from": "0x0D53B1035c840030B00dafb216a21E16Bf668895","to": "0x84EC5C1611f17759a997e303bEF45ee00c3647Cc", "value":"0x8ac7230489e80000",
        "data":"0x65726269653a7b2274797065223a322c22637362745f61646472657373223a22307838303030303030303030303030303030303030303030303030303030303030303030303030303031222c2276657273696f6e223a2276302e302e31227d"}],
        "id":20211209}' 127.0.0.1:8545