Recover online weight
======================
Description
-----------------
If validator's online weight is less than 70, the transaction can recover the weight.
Recovering weight need to consume ERB. The ERB consumed is (70 - current weight)/10.0 ERB.

Transaction Format
-------------------
.. code-block::

    {
          from: validator's address
          to: validator's address
          data:{
               erbie:{
                  type:5
                  version:"0.0.1"
               }
          }
    }

.. csv-table::
    :header: "Parameter", "Datatype", "Description"
    :widths: 10, 10, 30

    "from", "String(hexadecimal) ", "validator's address"
    "to", "String(hexadecimal) ", "validator's address"
    "type", "Int", "Transaction type, value: 5"
    "version", "String", "Version"

Examples
------------------------------
.. code-block::

    data part:

        erbie:{"type":5,"version":"v0.0.1"}

    transaction:
        Convert the above data part to a hexadecimal string and put it in the data section

        curl -X POST -H 'Content-Type: application/json' --data'{"jsonrpc":"2.0","method":"eth_sendTransaction",
        "params": [{"from": "0x0D53B1035c840030B00dafb216a21E16Bf668895","to": "0x0D53B1035c840030B00dafb216a21E16Bf668895",
        "data":"0x65726269653a7b2274797065223a352c2276657273696f6e223a2276302e302e31227d"}],
        "id":20211209}' 127.0.0.1:8545

