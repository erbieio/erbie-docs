================
Upgrade History
================

=========    ======================   =================================================================================================================================================================================
Version          Date                     Comments
=========    ======================   =================================================================================================================================================================================                               
v0.14.0       2023/07/21                1. Optimization of Blackhole Block broadcasting.
                                        2. Adjust to prevent related attacks of blackhole blocks. 
                                        3. Optimize blackhole block verification.
                                        4. Add and Optimize some ErbieChain transactions. 
                                        5. Optimize Account account structure, SNFT transaction log, Validator storage method, etc. 
v0.13.0       2023/03/20                1. Add validators using proxy API. 
                                        2. Add an API to get the real address.
v0.12.0       2023/02/06                1. Change the block generation strategy for blackhole blocks. 
                                        2. Increase verification of blackhole block consensus participants. 
                                        3. Modify the broadcast mode of blackhole blocks. 
                                        4. Optimize the initialization method of the exchange's memory pool. 
                                        5. Add SNFT merge transaction logs. 
                                        6. Optimize algorithms: logic when there are less than 11 validators.
                                        7. Add an interface to query coefficient changes.
v0.11.0       2022/12/26                 A series of bug fixes and performance improvements.
v0.10.0       2022/12/06                1. Added a shrink penalty mechanism. 
                                        2. Added a transaction to restore the validator weight coefficient: if the validator is not online for a long time, its weight coefficient will be very small, so it can't participate in the consensus, at which time it needs to be restored by initiating the transaction. 
                                        3. Adjusted the block generation logic between normal blocks and blackhole blocks to reduce the chance of having the same height normal block and blackhole block at the same time. 
                                        4. Added some verification of blackhole block data, such as signature data, difficulty value, etc. 
                                        5. The rewards of seven validators in each block are delayed to the next block for reward.
v0.9.0        2022/09/29                1. Added a surrounding chain random hash. 
                                        2. Added regular online check. 
                                        3. Added selection of validators.
                                        4. Optimize consensus algorithm.
v0.8.0        2022/07/11                 Optimized random discard algorithm and a series of performance improvements and bug fixes.
v0.7.0        2022/07/06                 First release online.
=========    ======================   =================================================================================================================================================================================
                      


