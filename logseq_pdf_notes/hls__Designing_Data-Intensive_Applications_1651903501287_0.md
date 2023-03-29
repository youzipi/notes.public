file-path:: ../assets/Designing_Data-Intensive_Applications_1651903501287_0.pdf

-
-
-
-
- xii.  Atomic commit is formalized slightly differently from consensus: an atomic transaction can commit onlyif all participants vote to commit, and must abort if any participant needs to abort. Consensus is allowed todecide on any value that is proposed by one of the participants. However, atomic commit and consensus arereducible to each other [70, 71]. Nonblocking atomic commit is harder than consensus—see “Three-phasecommit” on page 359.
  ls-type:: annotation
  hl-page:: 375
  id:: 627611e6-a279-4b6b-89e4-4c79c85aae68
- This  is  especially  important  for  multi-object  transac‐tions  (see  “Single-Object  and  Multi-Object  Operations”  on  page  228)  and  databasesthat  maintain  secondary  indexes.
  ls-type:: annotation
  hl-page:: 376
  id:: 62761659-c74c-4dc1-b5fe-56bba68038f3
- Thus,  on  a  single  node,  transaction  commitment  crucially  depends  on  the  order  inwhich data is durably written to disk: first the data, then the commit record [72]. Thekey  deciding  moment  for  whether  the  transaction  commits  or  aborts  is  the  momentat  which  the  disk  finishes  writing  the  commit  record:  before  that  moment,  it  is  stillpossible to abort (due to a crash), but after that moment, the transaction is commit‐ted (even if the database crashes).
  ls-type:: annotation
  hl-page:: 376
  id:: 6276198b-2739-4f94-855f-b264492517af
- For  this  reason,  a  node  must  only  commit  once  it  is  certain  that  allother nodes in the transaction are also going to commit.
  ls-type:: annotation
  hl-page:: 377
  id:: 62761d32-fa67-4f6d-b9b2-96d2cd811683
- [:span]
  ls-type:: annotation
  hl-page:: 378
  id:: 62762509-e4a3-41e9-9443-a7253a10afae
  hl-type:: area
  hl-stamp:: 1651909896253
- [:span]
  ls-type:: annotation
  hl-page:: 381
  id:: 62762e82-bbb1-4b35-a8d8-25e16ac2c612
  hl-type:: area
  hl-stamp:: 1651912321228
- Thus,  the  commit  point  of  2PC  comes  down  to  a  regular  single-nodeatomic commit on the coordinator.
  ls-type:: annotation
  hl-page:: 381
  id:: 62762f53-7ee7-4e6e-9c88-0596d09e1409
- Ordering Guarantees
  ls-type:: annotation
  hl-page:: 361
  id:: 62c97a31-36b0-4d0d-8a00-425f845502c8
- [:span]
  ls-type:: annotation
  hl-page:: 175
  id:: 62c98a56-fb4d-44d2-b2f0-23e0a083aecc
  hl-type:: area
  hl-stamp:: 1657375316524
- [:span]
  ls-type:: annotation
  hl-page:: 176
  id:: 62c98bdf-c837-4533-8cb9-277ab14432ec
  hl-type:: area
  hl-stamp:: 1657375707586
- there is no guarantee of how long it mighttake.
  ls-type:: annotation
  hl-page:: 176
  id:: 62caaeaa-9849-4a98-93a4-b58c779a6a4c
- or example, if a follower is recovering from a failure, if the systemis  operating  near  maximum  capacity,  or  if  there  are  network  problems  between  thenodes.
  ls-type:: annotation
  hl-page:: 176
  id:: 62caaeca-1c5a-4d34-8e0f-a8980047fd53
- if  the  synchronous  follower  doesn’t  respond
  ls-type:: annotation
  hl-page:: 176
  id:: 62caaef4-0e5c-45d3-9268-277b23ab918e
- the  write  cannot  be  processed.
  ls-type:: annotation
  hl-page:: 176
  id:: 62caaef7-b872-43a8-9d0a-43c8880a6a42
- block  all  writes  and  wait  until  the  synchronous  replica  is  availableagain.
  ls-type:: annotation
  hl-page:: 176
  id:: 62caaf01-78a7-4752-afbd-e8168f621ac2
- any  one  nodeoutage would cause the whole system to grind to a halt.
  ls-type:: annotation
  hl-page:: 176
  id:: 62caaf16-8282-4064-9e3e-5ad7fafd102d
- it  is  impractical  for  all  followers  to  be  synchronous:  any  one  nodeoutage would cause the whole system to grind to a halt.
  ls-type:: annotation
  hl-page:: 176
  id:: 62caaf35-b930-42cc-a77d-758460abf4b2
- you  have  an  up-to-date  copy  of  the  data  on  at  least  two  nodes
  ls-type:: annotation
  hl-page:: 176
  id:: 62cbd666-4676-4c5b-8da0-74b18b56fae9
- if the leader fails and is not recoverable, any writes that have not yet been repli‐cated  to  followers  are  lost.
  ls-type:: annotation
  hl-page:: 177
  id:: 62cbd6a6-c23b-4a7a-9b0c-f5767c01d06c
- the leader can continue processing writes, even if all of itsfollowers have fallen behind.
  ls-type:: annotation
  hl-page:: 177
  id:: 62cbd6e6-798d-4dcd-b6fa-13e5036c3688
- Weakening durability may sound like a bad trade-off, but asynchronous replication isnevertheless  widely  used,  especially  if  there  are  many  followers  or  if  they  are  geo‐graphically  distributed.
  ls-type:: annotation
  hl-page:: 177
  id:: 62cbd77a-7759-4667-a101-53eff412846d
- [8]  Robbert  van  Renesse  and  Fred  B.  Schneider:  “Chain  Replication  for  SupportingHigh Throughput and Availability,” at 6th USENIX Symposium on Operating SystemDesign and Implementation (OSDI), December 2004.
  ls-type:: annotation
  hl-page:: 216
  id:: 62cbda21-b971-48bb-803d-536cecdb4d15
- [9]   Jeff   Terrace   and   Michael   J.   Freedman:   “Object   Storage   on   CRAQ:   High-Throughput  Chain  Replication  for  Read-Mostly  Workloads,”  at  USENIX  AnnualTechnical Conference (ATC), June 2009.
  ls-type:: annotation
  hl-page:: 216
  id:: 62cbda32-79b7-4310-b6c2-51ad3e0e3a8a
- [10]  Brad  Calder,  Ju  Wang,  Aaron  Ogus,  et  al.:  “Windows  Azure  Storage:  A  HighlyAvailable Cloud Storage Service with Strong Consistency,” at 23rd ACM Symposiumon Operating Systems Principles (SOSP), October 2011.
  ls-type:: annotation
  hl-page:: 216
  id:: 62cbda7a-5b9c-4353-af05-cc4bc503bbd2
- There  is  a  strong  connection  between  consistency  of  replication  and  consensus  (get‐ting several nodes to agree on a value)
  ls-type:: annotation
  hl-page:: 177
  id:: 62cbdb36-7e05-491a-a87f-9b0a5b1ee550
- caught  up
  ls-type:: annotation
  hl-page:: 178
  id:: 62cbdd94-f708-4d27-a346-df76b51c497a
- position
  ls-type:: annotation
  hl-page:: 178
  id:: 62cbde14-8f87-40de-86f9-3f8516cd6093
- keep the system as awhole running despite individual node failures, and to keep the impact of a node out‐age as small as possible.
  ls-type:: annotation
  hl-page:: 178
  id:: 62cbdeaa-cddd-42fa-b178-f668b695a7d2
- the  last  transaction
  ls-type:: annotation
  hl-page:: 178
  id:: 62cbe04e-8233-4adc-8db9-e04693a66ec6
- There  is  nofoolproof  way  of  detecting  what  has  gone  wrong,  so  most  systems  simply  use  atimeout:
  ls-type:: annotation
  hl-page:: 179
  id:: 62ccde01-fc43-47ad-9b2a-1455ef4efc39
- the replica with the most up-to-date data changes from theold  leader  (to  minimize  any  data  loss).
  ls-type:: annotation
  hl-page:: 179
  id:: 62ccdede-c356-481b-9f6a-d75827c1c3a1
- discarded
  ls-type:: annotation
  hl-page:: 179
  id:: 62ccebe3-08ae-4271-882f-96c92aec3a60
- all thewrites
  ls-type:: annotation
  hl-page:: 179
  id:: 62ccebeb-34ee-47db-965e-6504a8f8cfc7
- other  storage  systems  outside  of  thedatabase need to be coordinated with the database contents
  ls-type:: annotation
  hl-page:: 179
  id:: 62cd1335-665a-4532-82fc-a065cd06f476
- split brain
  ls-type:: annotation
  hl-page:: 180
  id:: 62cd139b-e2a7-4771-adf4-ede3acad8fa3
- a mechanism to shut down onenode  if  two  leaders  are  detected
  ls-type:: annotation
  hl-page:: 180
  id:: 62cd13b2-e910-48d7-92c1-c05d53964d99
- right
  ls-type:: annotation
  hl-page:: 180
  id:: 62cd13d7-4d0e-43b6-b04f-2e4b7eb1cd57
- There  are  no  easy  solutions  to  these  problems.  For  this  reason,  some  operationsteams  prefer  to  perform  failovers  manually,  even  if  the  software  supports  automaticfailover.
  ls-type:: annotation
  hl-page:: 180
  id:: 62cd1572-7cc5-4af1-91ee-5366c7739c5a
- autoincrementing
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd1797-f49a-4fd3-9010-840e289150fb
- nondeterministic  function
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd179b-f9e3-4cfc-87a0-2f606a40c58f
- NOW()
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd179e-c72d-433c-865f-e56b1ef2337f
- RAND()
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd17a2-143c-4587-ade6-2bb36af5eed8
- depend on the existingdata
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd17ad-a2ad-4def-8555-dbebd6590856
- ame order
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd17b6-325a-4143-9be2-f5866686f47e
- side  effect
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd17d3-0fa9-4751-8a5a-afb2f82ced4c
- deterministic
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd17e6-4bd3-4e66-9e45-fef179ef9a5f
- replace  anynondeterministic  function  calls  with  a  fixed  return  value
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd1856-b4b1-4871-ab4b-04cf9bfffc5e
- so manyedge cases
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd1864-48c3-4100-a50c-42da66ab0e76
- the  exact  same  log
  ls-type:: annotation
  hl-page:: 181
  id:: 62cd42ef-39fa-4daf-b05b-823585e24d42
- very low level:
  ls-type:: annotation
  hl-page:: 182
  id:: 62cd43d5-1b90-4506-91ba-82832c3e6ef1
- details  of  which  bytes  were  changed  in  which  disk  blocks.
  ls-type:: annotation
  hl-page:: 182
  id:: 62cd43ec-0505-4bab-b573-560806a2fd18
- closely coupled to
  ls-type:: annotation
  hl-page:: 182
  id:: 62cd4408-2574-4e7a-ab43-02584924b3f9
- zero-downtime
  ls-type:: annotation
  hl-page:: 182
  id:: 62cd4e12-916e-4061-9fd2-be672831703f
- decoupled  from  the  storage  engineinternals
  ls-type:: annotation
  hl-page:: 182
  id:: 62cd57f5-579e-4495-9b55-d7c6a736142e
- at the granularity of a row
  ls-type:: annotation
  hl-page:: 182
  id:: 62cd58be-5988-4366-87f8-eb2206646a92
- asier for external applications to parse.
  ls-type:: annotation
  hl-page:: 182
  id:: 62cd59cf-f191-49b2-aa48-88c55a8ac07f
- backward  compatible
  ls-type:: annotation
  hl-page:: 182
  id:: 62cd59df-9f12-4b92-bb69-23880d57e022
- change data capture
  ls-type:: annotation
  hl-page:: 183
  id:: 62cd5a96-f808-43ca-ae07-41d29b371927
- more  flexibility
  ls-type:: annotation
  hl-page:: 183
  id:: 62cd5b03-9688-4776-aa6f-5d7d8ba6c452
- replicate  from  one  kind  ofdatabase  to  another
  ls-type:: annotation
  hl-page:: 183
  id:: 62cd5b2c-e2b0-490c-bcf7-1fb28630f4dd
- conflict  resolution  logic
  ls-type:: annotation
  hl-page:: 183
  id:: 62cd5b31-eaed-4a21-937d-94c281be04b5
- only  replicate  a  subset  of  the  data
  ls-type:: annotation
  hl-page:: 183
  id:: 62cd5b5d-8c48-4087-b8c9-78b774464852
- applicationlayer
  ls-type:: annotation
  hl-page:: 183
  id:: 62cd5b9d-20ae-48f7-abef-c37d0f4b073f
- triggers and stored procedures
  ls-type:: annotation
  hl-page:: 183
  id:: 62cd5d24-4cc8-494b-933b-f66d76219bc2
- hasthe opportunity to log this change into a separate table
  ls-type:: annotation
  hl-page:: 183
  id:: 62ce30a5-1e06-4c7e-a3e7-b7fb593c894c
- greater  overheads
  ls-type:: annotation
  hl-page:: 183
  id:: 62ce315c-d8e8-4a62-8cf8-d9cfb7632677
- more prone to bugs and limitations t
  ls-type:: annotation
  hl-page:: 183
  id:: 62ce3161-7b35-49c1-9703-5681c803652e
- consist  of  mostly  reads  andonly a small percentage of writes (a common pattern on the web),
  ls-type:: annotation
  hl-page:: 183
  id:: 62ce3323-9bdd-420a-95cf-66ec1427f688
- the  more  nodes  you  have,  the  likelier  it  is  that  one  willbe down, so a fully synchronous configuration would be very unreliable.
  ls-type:: annotation
  hl-page:: 184
  id:: 62ce3770-34d2-47ee-879b-029ce99b9368
- However,  this  approach  only  realisticallyworks  with  asynchronous  replication
  ls-type:: annotation
  hl-page:: 183
  id:: 62ce377d-3f42-435a-92df-b3a2f6bdadb3
- ventually catch up and become consis‐tent with the leader
  ls-type:: annotation
  hl-page:: 184
  id:: 62ce380e-3532-4045-975d-6e3f33150591
- vague
  ls-type:: annotation
  hl-page:: 184
  id:: 62ce38a8-ceaa-4642-b088-c3e15ae53c4e
- how far
  ls-type:: annotation
  hl-page:: 184
  id:: 62ce38ac-d551-483c-90d9-898354d28c64
- [:span]
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce3ba7-6a0b-4dbc-925e-43df950441b8
  hl-type:: area
  hl-stamp:: 1657682854775
- read-after-write consistency
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce3bfd-832d-4a11-a068-4e5116e85876
- read-your-writesconsistency
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce3c01-411d-4351-a462-ee702f38b590
- This requires that you have some wayof  knowing  whether  something  might  have  been  modified,  without  actuallyquerying  it.
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce3f69-e5c2-4620-9980-d611ff3bef17
- other  criteria
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce3ffb-ca0f-41dd-b5ed-3812c43ed6a1
- track thetime  of  the  last  update
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce3fff-26d7-4a18-9d5b-a0c32415f8b1
- for  one  minute  after  the  last  update
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce4005-c56b-4939-ae45-99ed3d46e019
- client
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce400f-29fd-46fa-84d2-5f30252bf92e
- he  timestamp  of  its  most  recent  write—
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce401b-58de-4524-a288-1377f34bdf62
- sufficiently up to date
  ls-type:: annotation
  hl-page:: 185
  id:: 62ce66e2-ac65-4b31-955b-7b8f8e38251c
- logical timestamp
  ls-type:: annotation
  hl-page:: 186
  id:: 62ce66fe-e24e-46e1-9d73-933ed1860d3b
- multiple  datacenters
  ls-type:: annotation
  hl-page:: 186
  id:: 62ce67a2-358e-4190-bb23-ec3fa613acaa
- e routed to the datacenter that con‐tains the leader
  ls-type:: annotation
  hl-page:: 186
  id:: 62ce67a6-b7a1-4c89-9c0f-a1c6f5c3ffe0
- cross-device read-after-write consistency
  ls-type:: annotation
  hl-page:: 186
  id:: 62ce688f-1a75-43a6-85d1-800aa2315f23
- centralized
  ls-type:: annotation
  hl-page:: 186
  id:: 62ce68c0-11ae-4bf6-aa4c-fb282a880f08
- moving backward in time
  ls-type:: annotation
  hl-page:: 186
  id:: 62ce6983-51d1-4cc7-b1d7-6e1a94333e83
- [:span]
  ls-type:: annotation
  hl-page:: 187
  id:: 62ce6a00-e6f6-4c2c-aa67-40ef91b58ec3
  hl-type:: area
  hl-stamp:: 1657694719212
- they will not see time go backward
  ls-type:: annotation
  hl-page:: 187
  id:: 62ce7233-15c5-4144-9596-400b0e7d1d89
- [:span]
  ls-type:: annotation
  hl-page:: 188
  id:: 62ce744d-c15b-4dec-a235-554353baf726
  hl-type:: area
  hl-stamp:: 1657697355886
- if a sequence of writes happens in a certain order,then anyone reading those writes will see them appear in the same order
  ls-type:: annotation
  hl-page:: 188
  id:: 62ce7574-c42a-4a42-b6e7-1648512bcd5f
- causally related to each other
  ls-type:: annotation
  hl-page:: 189
  id:: 62ce76d8-2596-4141-86f2-d53f11aa835c
- Pretending that replication is synchronous
  ls-type:: annotation
  hl-page:: 189
  id:: 62ce78f4-6714-4a93-bfd2-8d7a04ddbf36
- stronger
  ls-type:: annotation
  hl-page:: 189
  id:: 62ce78fc-e6aa-44f6-84cc-76e481174870
- This  is  whytransactions exist
  ls-type:: annotation
  hl-page:: 189
  id:: 62ce7946-e885-4c46-8873-fdff3783a6fa
- asserting  that  eventual  consistency  is  inevitable  in  a  scalable  system
  ls-type:: annotation
  hl-page:: 189
  id:: 62ce7ae7-e462-409c-b8c4-23e8925e4d70
- recurring
  ls-type:: annotation
  hl-page:: 361
  id:: 62ce7f1c-a72b-4436-9f98-85e8f1120ff8
- determine the order of writes in the replication log
  ls-type:: annotation
  hl-page:: 361
  id:: 62ce7f3b-1d32-4e32-965f-a505326e1802
- the order inwhich followers apply those writes
  ls-type:: annotation
  hl-page:: 361
  id:: 62ce7f4f-5849-4b52-9284-d769bcd4e91d
- as if they were executed in some sequential order.
  ls-type:: annotation
  hl-page:: 361
  id:: 62ce7fc0-a1f9-46e8-9db6-bbe95fa64bed
- while preventing serialization conflicts
  ls-type:: annotation
  hl-page:: 361
  id:: 62ce7fd2-ef8b-48e7-9c2e-d4edcde9d079
- introduce  order  into  a  disorderly  world
  ls-type:: annotation
  hl-page:: 361
  id:: 62ce8065-80b8-4526-b77b-c7ebadecc79d
- causal dependency
  ls-type:: annotation
  hl-page:: 361
  id:: 62ce8385-6d26-4776-a949-c244a4e79070
- a row must first be created before it can be updated.
  ls-type:: annotation
  hl-page:: 362
  id:: 62ce83a0-45af-4df6-a726-dd1712b023a3
- happened before
  ls-type:: annotation
  hl-page:: 362
  id:: 62ce83db-cf9a-4bbf-800c-62371807192a
- ei‐ther knew about the other
  ls-type:: annotation
  hl-page:: 362
  id:: 62ce83e7-8e9b-4798-8d9e-0874386793fe
- B  mighthave known about A,
  ls-type:: annotation
  hl-page:: 362
  id:: 62ce83f1-4e51-47e7-a3ca-97dbf3840262
- consistentwith causality
  ls-type:: annotation
  hl-page:: 362
  id:: 62ce8411-f2fe-49ac-9481-b197a8df6c97
- if the snapshot contains an answer, it must also contain the ques‐tion being answered
  ls-type:: annotation
  hl-page:: 362
  id:: 62ce8416-fd06-49aa-b738-63468a2b748e
- au‐sally  before
  ls-type:: annotation
  hl-page:: 362
  id:: 62ce843f-319f-456f-a75f-91e6ddf30fc2
- Atomicity,  isolation,  and  durability  are  properties  of  the  database,  whereas  consis‐tency (in the ACID sense) is a property of the application. The application may relyon  the  database’s  atomicity  and  isolation  properties  in  order  to  achieve  consistency,but it’s not up to the database alone. Thus, the letter C doesn’t really belong in ACID.i
  ls-type:: annotation
  hl-page:: 247
  id:: 62d3b361-4bbb-4dff-876d-5516146d4a04
- (Systems  that  do  not  meet  the  ACID  criteria  are  sometimes  called  BASE,  whichstands  for  Basically  Available,  Soft  state,  and  Eventual  consistency  [9].  This  is  evenmore vague than the definition of ACID. It seems that the only sensible definition ofBASE is “not ACID”; i.e., it can mean almost anything you want.)
  ls-type:: annotation
  hl-page:: 245
  id:: 62d3b97e-e94c-4319-b131-a9b74b751eed
  hl-stamp:: 1680082695087
  hl-color:: yellow
- a network with bounded delay and nodes with bounded response times
  ls-type:: annotation
  hl-page:: 381
  hl-color:: yellow
  id:: 636b2397-afb3-495a-bcdd-a26fdd597d7f
- perfect failure detector
  ls-type:: annotation
  hl-page:: 381
  hl-color:: yellow
  id:: 636b447f-6bd9-43ff-865a-d44a89530e27
- Capturing the happens-before relationship
  ls-type:: annotation
  hl-page:: 209
  hl-color:: yellow
  id:: 63a917da-a990-4d47-b8aa-23709cd20232
- Once we have worked out how to do this on a single replica, we can generalize the approach to a leaderless database with multiple replicas.
  ls-type:: annotation
  hl-page:: 210
  hl-color:: yellow
  id:: 63a918a0-6416-4bd8-882b-0d8b7d6f4575
- It then returns both values to the client, along with the version number of 2
  ls-type:: annotation
  hl-page:: 210
  hl-color:: yellow
  id:: 63a942fb-dd39-4434-9ad9-3330a313cd2b
- so the client now merges those values and adds ham to form a new value, [eggs, milk, ham]
  ls-type:: annotation
  hl-page:: 210
  hl-color:: yellow
  id:: 63a94409-890d-4e02-bb1f-991cfe62b2cc
- the server can determine whether two operations are concurrent by looking at the version numbers—it does not need to interpret the value itself
  ls-type:: annotation
  hl-page:: 211
  hl-color:: yellow
  id:: 63a9448f-7e43-43c5-8ca3-97a64ca32821
- When a client writes a key, it must include the version number from the prior read, and it must merge together all values that it received in the prior read
  ls-type:: annotation
  hl-page:: 212
  hl-color:: yellow
  id:: 63a944cc-8a8a-4f6b-923d-de8dd52ba599
- When the server receives a write with a particular version number, it can over‐ write all values with that version number or below (since it knows that they have been merged into the new value)
  ls-type:: annotation
  hl-page:: 212
  hl-color:: yellow
  id:: 63a945be-cc6e-4cdc-94ec-ee13b50a7bf1
- When a write includes the version number from a prior read, that tells us which pre‐ vious state the write is based on
  ls-type:: annotation
  hl-page:: 212
  hl-color:: yellow
  id:: 63a94610-fcca-4f5c-879d-714df6265fd6
- [:span]
  ls-type:: annotation
  hl-page:: 211
  hl-color:: yellow
  id:: 63a94748-2abb-43fc-a0b2-55f84f1d4519
  hl-type:: area
  hl-stamp:: 1672038215591
- Merging sibling values is essentially the same problem as conflict resolution in multileader replication
  ls-type:: annotation
  hl-page:: 212
  hl-color:: yellow
  id:: 63a9475f-14fe-4df3-b938-c1f37d79c4b9
- instead, the system must leave a marker with an appropriate version number to indicate that the item has been removed when merging siblings. Such a deletion marker is known as a tombstone.
  ls-type:: annotation
  hl-page:: 213
  hl-color:: yellow
  id:: 63a947c7-f5be-4384-9d09-8a081b08bc1b
- [:span]
  ls-type:: annotation
  hl-page:: 211
  hl-color:: yellow
  id:: 63a94c4c-5320-4d46-bed3-d457b187bae6
  hl-type:: area
  hl-stamp:: 1672039498927
- However, in practice, one database’s implementation of ACID does not equal another’s implementation. For example, as we shall see, there is a lot of ambiguity around the meaning of isolation [8]. The high-level idea is sound, but the devil is in the details. Today, when a system claims to be “ACID compliant,” it’s unclear what guarantees you can actually expect. ACID has unfortunately become mostly a mar‐ keting term.
  ls-type:: annotation
  hl-page:: 245
  hl-color:: yellow
  id:: 64240736-df7d-4f2c-b9f8-e00819c9d6f6