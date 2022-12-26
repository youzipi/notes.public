file-path:: ../assets/Replicated_Data_Consistency_Explained_Through_Baseball_62d0d81228d144221224b896_main_1657854073911_0.pdf

- file-path:: ../assets/Replicated_Data_Consistency_Explained_Through_Baseball_62d0d81228d144221224b896_main_1657854073911_0.pdf
  file:: [Replicated_Data_Consistency_Explained_Through_Baseball_62d0d81228d144221224b896_main_1657854073911_0.pdf](../assets/Replicated_Data_Consistency_Explained_Through_Baseball_62d0d81228d144221224b896_main_1657854073911_0.pdf)
  title:: hls__Replicated_Data_Consistency_Explained_Through_Baseball_62d0d81228d144221224b896_main_1657854073911_0
- During a baseball game, for example, different participants (the scorekeeper, umpire, sportswriter, and so on) benefit from six different consistency guarantees when reading the current score.
  ls-type:: annotation
  hl-page:: 1
  id:: 62d0df3d-d74a-4345-ba98-92f60e502070
- Amazon’s SimpleDB
  ls-type:: annotation
  hl-page:: 1
  id:: 62d0e180-b1b3-41f8-854e-26174804ec1b
- Google App Engine Datastore
  ls-type:: annotation
  hl-page:: 1
  id:: 62d0e186-ec65-4849-b08a-a57aa11c0ce1
- PNUTS
  ls-type:: annotation
  hl-page:: 1
  id:: 62d0e208-35b5-41ec-a840-0a33029120cb
- no more than 5 minutes out-of-date
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e372-44b0-46be-965b-3ffa3a3bdbbc
- always observes the results of its own writes
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e379-0a6e-4ea8-b1de-2609b1e745b5
- being less-than-useful
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e3af-89ff-493c-b600-4ce6204400a9
- there are fundamental tradeoffs between consistency, performance, and availability.
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e412-3eca-4970-9b2f-01b4211b1846
- occupies some point
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e425-42ee-4954-8948-01c9e210d460
- But are different consistencies useful in practice?  Can applicationdevelopers cope with eventual consistency?  Should cloud storage systems offer an even greater choice of consistency than the consistent and eventually consistent reads offered by Amazon’s SimpleDB?
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e4e7-31bd-43ef-8fb8-4a8d958fc1f3
- sixpossible consistency guarantees for read operations
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e5dd-ca14-4aea-b9a2-4ccd2f2c3b83
- examines the roles of various people who want to access the baseball score and the read consistency that each desires
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e5ec-3d3e-47d9-ae87-f47e2cfd7b8c
- draw conclusions from this simple example
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e5f4-268b-4212-9bef-771cd8dd7f8f
- presents an algorithm that emulates a baseball game
  ls-type:: annotation
  hl-page:: 2
  id:: 62d0e603-076d-42b1-95a2-38fb331e623e
- can be described in a simple, implementation-independent way.
  ls-type:: annotation
  hl-page:: 2
  id:: 62d10425-a2ed-47f6-b6a1-669d20ce25dc
- [:span]
  ls-type:: annotation
  hl-page:: 3
  id:: 62d1049d-f538-4bcb-8515-6549b2138b58
  hl-type:: area
  hl-stamp:: 1657865372808
- an ordered sequence of writes starting with the first write
  ls-type:: annotation
  hl-page:: 3
  id:: 62d10a15-253b-4d18-886b-9546ea8804a6
- not too out-of-date
  ls-type:: annotation
  hl-page:: 3
  id:: 62d10a5f-81a8-4914-b51d-f6e5fa845167
- the number of missing writes
  ls-type:: annotation
  hl-page:: 3
  id:: 62d11ed8-2435-400c-b3fd-4963f527cc8b
- the amount of inaccuracy
  ls-type:: annotation
  hl-page:: 3
  id:: 62d11ee0-c240-4cbc-a768-4ec52d6e6608
- most natural concept
  ls-type:: annotation
  hl-page:: 3
  id:: 62d11ee6-677f-44f4-bcc6-63beaa8c88c2
- session guarantee
  ls-type:: annotation
  hl-page:: 3
  id:: 62d1272b-67b4-42e0-a320-a121927bb768
- increasingly up-to-dateover time
  ls-type:: annotation
  hl-page:: 3
  id:: 62d12730-e4a2-4964-9780-a0ac76e82336
- stronger
  ls-type:: annotation
  hl-page:: 4
  id:: 62d1287c-73d8-47a4-9b96-b91ed7494803
- a form of eventual consistency
  ls-type:: annotation
  hl-page:: 4
  id:: 62d12880-c307-4f68-9a89-37d1e2e9e6ee
- stronger than
  ls-type:: annotation
  hl-page:: 4
  id:: 62d12885-3fb0-4715-987a-d0357f398266
- each might result in a read operation returning a different value
  ls-type:: annotation
  hl-page:: 4
  id:: 62d12898-df71-4fd0-bcf6-885f9acd6795
- [:span]
  ls-type:: annotation
  hl-page:: 5
  id:: 62d12f61-f604-4976-af39-9dbd6946420b
  hl-type:: area
  hl-stamp:: 1657876320349
- But, the general comparisons between the various consistency guarantees are qualitatively accurate
  ls-type:: annotation
  hl-page:: 4
  id:: 62d12f80-7d90-435b-924d-4cabbcc5694c
- Labeling each cell in this table is not an exact science
  ls-type:: annotation
  hl-page:: 4
  id:: 62d12fa3-6ff2-4640-b60b-3df46ced4f24
- The bottom line is that one faces substantial trade-offs when choosing a particular replication scheme with a particular consistency model.
  ls-type:: annotation
  hl-page:: 4
  id:: 62d12ff8-8cd3-4aa4-af50-0f3b2de7d65d
- [:span]
  ls-type:: annotation
  hl-page:: 5
  id:: 62d144e5-e137-479c-b89a-549682f885f6
  hl-type:: area
  hl-stamp:: 1657881828853
- [:span]
  ls-type:: annotation
  hl-page:: 6
  id:: 62d145a2-b964-44ea-8274-04b5523b1e47
  hl-type:: area
  hl-stamp:: 1657882017382
- [:span]
  ls-type:: annotation
  hl-page:: 6
  id:: 62d14671-20a3-4275-a0ed-c3730cfac2f9
  hl-type:: area
  hl-stamp:: 1657882224245
- many of these scores are ones that were never the actual score
  ls-type:: annotation
  hl-page:: 7
  id:: 62d14844-d23e-4e5c-ab2b-1f5d42ed44f9
- actually existed at some time.
  ls-type:: annotation
  hl-page:: 7
  id:: 62d1485c-89d6-4af5-9c58-cdefd0166604
- for a bound of 7 innings or more, the result set is the same as for eventual consistencyin this example
  ls-type:: annotation
  hl-page:: 7
  id:: 62d161c1-a8e3-46a9-b347-752df31ae3ca
- may even find that the data they are requesting is not currently available
  ls-type:: annotation
  hl-page:: 7
  id:: 62d1658d-36c7-493e-b9fb-e6b699723040
- for each participant, the minimumconsistency that is required
  ls-type:: annotation
  hl-page:: 7
  id:: 62d165c3-ff9d-4a86-9293-294fec0a7250
- [:span]
  ls-type:: annotation
  hl-page:: 7
  id:: 62d1666d-a4fd-41c1-a086-362a9c990c17
  hl-type:: area
  hl-stamp:: 1657890412660
- the onlyperson who updates the score
  ls-type:: annotation
  hl-page:: 8
  id:: 62d169d6-2afc-40cf-a629-d3736ae4d389
- [:span]
  ls-type:: annotation
  hl-page:: 8
  id:: 62d3c54e-247f-4551-83b2-fdd6ca310c4e
  hl-type:: area
  hl-stamp:: 1658045773254
- [:span]
  ls-type:: annotation
  hl-page:: 9
  id:: 62d3c9c1-e12e-4a63-a8b4-44f0bcb05fb8
  hl-type:: area
  hl-stamp:: 1658046912830
- may return scores that never existed.
  ls-type:: annotation
  hl-page:: 9
  id:: 62d3ce15-e66c-4e8b-9416-09133ff4603c
- requests the monotonic readsguarantee in addition to requesting a consistent prefix
  ls-type:: annotation
  hl-page:: 9
  id:: 62d3d095-4d4f-4f0d-a91f-596383b4194b
- [:span]
  ls-type:: annotation
  hl-page:: 10
  id:: 62d3d434-9f83-423f-b555-c11a311cc72a
  hl-type:: area
  hl-stamp:: 1658049587110
- [:span]
  ls-type:: annotation
  hl-page:: 10
  id:: 62d3dd73-697e-4ff7-bb7f-ac273117997b
  hl-type:: area
  hl-stamp:: 1658051954548
- read my writes
  ls-type:: annotation
  hl-page:: 11
  id:: 62d3de3d-b344-4630-9b2e-77b779d75386
- strongconsistency
  ls-type:: annotation
  hl-page:: 11
  id:: 62d3de46-82f9-495a-94a8-572f874f8f0e
- [:span]
  ls-type:: annotation
  hl-page:: 11
  id:: 62d3ded7-d6fe-4f12-b622-f20385c6a58a
  hl-type:: area
  hl-stamp:: 1658052310375
- balance the read workload
  ls-type:: annotation
  hl-page:: 11
  id:: 62d3e043-c28a-4169-bbc3-0023ee3b680c
- multiple guarantees must be combined
  ls-type:: annotation
  hl-page:: 12
  id:: 62d3e080-f41c-40f6-8245-5ac0de27f4ce
- different guarantees are desired
  ls-type:: annotation
  hl-page:: 12
  id:: 62d3e092-17ec-45e8-abc9-54ce16be649b
- he can obtain strongly consistent data even when issuing a weakly consistent read using a read my writesor bounded stalenessguarantee
  ls-type:: annotation
  hl-page:: 12
  id:: 62d3e0a7-d59f-4d3d-b037-e8f6a62e9613
- increases the burden on application developers
  ls-type:: annotation
  hl-page:: 12
  id:: 62d512f6-da5d-4be1-b6ea-d69f39098df7
- 6.Additional Readings
  ls-type:: annotation
  hl-page:: 13
  id:: 62d513cd-156d-4d72-b2b4-babbac4d77b1
- tangible
  ls-type:: annotation
  hl-page:: 13
  id:: 62d51547-3271-466e-b669-a9e1a35994c2
- This suggests that cloud storage systems should at least consider offering a largerchoice of read consistencies
  ls-type:: annotation
  hl-page:: 13
  id:: 62d51584-a663-4fa1-9cac-1d2014a95f2d
- Allowing cloud storageclients to read from diversereplicaswith achoice of consistency guarantees
  ls-type:: annotation
  hl-page:: 13
  id:: 62d515da-037b-4ae5-b135-923ed19d0930
