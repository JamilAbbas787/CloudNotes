# Chapter 5 - Simple Storage Service (S3)

## S3

____

- S3 Standard
  - Availability --- 4 9s (99.99%)
  - Durability --- 11 9s (99.999999999 %)
- Global namespace (Bucket names should be unique)
- Minimum size of objects is 0 bytes, maximum is 5TB
- Files can be uploaded in buckets which are nothing but folders hosting the files
- On successful upload, S3 returns a HTTP 200 status code
- By default all buckets are private

## S3 Consistency Model

____

Read after write consistency for new PUT objects (Newly uploaded objects are guaranteed to be read immediately without any stale state or problems)

Eventual consistency for overwrite PUTs and DELETEs (Modifications / deletions will eventually reflect latest state --- there could be a delay of some seconds)

## S3 Object Properties

____

- *Key* : Name of the object
- *Value* : Sequence of bytes/contents of the object
- *Versioning* : Version of the object
- *Metadata* : Objects can further have metadata (data about data) to classify the contents

## S3 Storage Tiers

____

S3 offers various storage tiers that help control cost, availability and durability of the data

- S3 Standard
  - This is the most costly alternative with 99.99% availability (probability that the object will be available when needed) and 99.999999999% durability (probability that data will not be lost)
- S3 IA (Infrequently accessed)
  - This still replicates data to different zones in a region but less costlier than standard. Retrieval fees are charged
- S3 IA 1 Zone
  - Multiple zones replication is not done and costs even lesser than S3 IA
- S3 Intelligent Tiering
  - Storage tiering is managed by AWS instead which uses Machine learning to decide on which tier to use for the bucket based on historical patterns of usage
- S3 Glacier
  - Used when cost has to be less but time of retrieval can be configurable ranging from minutes to hours
- S3 Glacier deep archive
  - This is cheapest option where retrieval time of more than 12 hours is acceptable. This is used for data which might be rarely needed and time of retrieval being around ~12 hours is still acceptable

## S3 Security Policies

____

- Access to S3 object/bucket can be controlled with ACL control lists or Bucket Policies
- Bucket policies work at bucket level BUT Access Control Lists can go all the way down to individual objects
- Access logging can be configured for S3 buckets which logs all access requests for S3, made by different users
- Encryption in transit is achieved by HTTPS (SSL / TLS)

Encryption at rest is achieved in two ways

- Service Side encryption (Can be further managed by AWS in three ways)
  - Keys managed by S3 service for encryption (**SSE-S3**)*
  - Keys provisioned by user in KMS (**SSE-KMS**)*
  - User/Customer provided encryption keys can also be used (**SSE-C**)*
- Client Side encryption
  - Client himself manages the encryption/decryption and uploads the encrypted data only

## S3 Versioning

____

- S3 versioning can be used to maintain multiple copies of objects
- Once enabled, it cannot be disabled on the same bucket

## S3 Transfer Acceleration

____

This is used to speed up large data uploads to S3. With this, user can upload the data to nearest edge location and S3 will then ensure that the data is replicated to the actual bucket for final storage. For Edge Location -> S3, AWS will then use the backbone network which is quite fast than the usual internet speed

## S3 Lifecycle Rules

____

- LRs can be used to automatically expire objects based on prefix/tag filters (For eg. All objects having tags "*abc"* should expire after 30 days)
- Objects can automatically transition across different storage tiers' based on lifecycle rules. For eg. after 30 days migrate objects to IA-1Zone and after 60 days move it to Glacier and finally expire them after 120 days

## S3 Cross Region Replication

____

- This is used when you want to replicate the contents of a bucket automatically to another bucket (The destination bucket could also enforce different storage tiers on the objects)
- Versioning has to be mandatorily enabled on both source and destination buckets
- Delete markers OR object deletions are not replicated on the destination bucket. This is done intentionally by Amazon to inadvertently replicating deletion of objects

## Object Lock

____

- Object Lock (WORM - Write Once, Read Many)
  - S3
    - Governance mode - User can still overwrite or deleta and object, but need special permissions
    - Compliance mode - No one (including root user) can overwrite or delete the object
  - Glacier Vault Lock
    - enforce compliance rules in a vault lock
    - once locked, the ploicy cannot be changed

## Other S3 Related Services Offered by AWS

____

- S3 Athena --- S3 Select based query analysis on S3 objects without transferring the data first to a data lake
- S3 Inventory --- Reporting for auditing purposes of all S3 objects. Reports can be stored in json, yaml or parquet format
- S3 Batch Operations : Run lambda function or other operations on millions of objects in one go

![image](https://user-images.githubusercontent.com/42945500/145450615-05fcc021-f2d8-460a-af39-1b9c243f04fc.png)
![image](https://user-images.githubusercontent.com/42945500/145450622-49e925b9-eec3-4223-bd2f-dd133c6e96bf.png)
![image](https://user-images.githubusercontent.com/42945500/145450632-07b3160c-9619-4935-bd86-f6a38a51a5a1.png)
![image](https://user-images.githubusercontent.com/42945500/145450646-cf958a33-d4e5-4c16-bde8-185d113a2ae3.png)
![image](https://user-images.githubusercontent.com/42945500/145450652-71e08867-1200-4eb3-be39-e15697352de7.png)
![image](https://user-images.githubusercontent.com/42945500/145450664-47a03b7b-ee9a-49f2-803b-1c4a1f55fc0e.png)
![image](https://user-images.githubusercontent.com/42945500/145450691-d987dacd-bac8-46db-9109-fb40ae0f69fc.png)
![image](https://user-images.githubusercontent.com/42945500/145450714-29154b22-1b5e-4843-ad42-4dec18a6db81.png)
![image](https://user-images.githubusercontent.com/42945500/145450718-bc7cd791-559f-468c-ab07-b113922539cd.png)
![image](https://user-images.githubusercontent.com/42945500/145450728-196a9b2b-5d22-4f6b-987d-8efdb344c61d.png)
![image](https://user-images.githubusercontent.com/42945500/145450743-839093d5-684e-4c7f-b1d2-60509ef61f3d.png)
![image](https://user-images.githubusercontent.com/42945500/145450754-31b5fea8-2a00-49aa-b730-ea71c0aec0a1.png)
![image](https://user-images.githubusercontent.com/42945500/145450768-eca7851d-e05f-4ca3-8285-5c1a2e21e636.png)
![image](https://user-images.githubusercontent.com/42945500/145450778-f1e4885b-e0d7-44bf-bdc4-8b3a7b2f432f.png)
![image](https://user-images.githubusercontent.com/42945500/145450802-5eee5f67-1a60-4403-b9c3-73a410b29af4.png)
![image](https://user-images.githubusercontent.com/42945500/145450833-a930ba69-89c8-4781-a9b5-4b80dd1e2d68.png)
