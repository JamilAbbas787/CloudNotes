# Chapter 4 - Identity and Access Management (IAM)

IAM (Identity and Access management)
______

- Users
  - Can be an IAM user or an applications accessing the AWS resources

- Groups
  - Group of users who can be collectively permitted some actions

- Roles (Who you are ?)
    - This is something which can be assumed by an entity like User or Group (This is similar to Authentication)

- Policies (What you can do?)
    - This defines the permissions you have on the resources that you want to access (This is similar to Authorization)

By default, new users have:

- only access_key_id and secret_access_key, but no console access

- no permissions, until they are made member of a group or assigned some roles/policies

IAM, like other AWS services is eventually consistent as this data is replicated across multiple servers. IAM is a global service (Not scoped per region). Mainly two services can allow access without authentication / authorization in AWS --- STS and S3

Request Context: This is the request object which AWS receives when somebody tries to access something or take an action on some AWS resource. This object includes source IP, resources that you are trying to access, what actions are you taking on those resources, what time of day this request originated etc.

Policies can be managed in two ways:

- Managed policies : AWS Managed & Customer Managed

- Inline Policies

Policies can further be of two types:

- Identity based policies : These are attached directly to Identities like User/Groups etc. They can be managed or inline policies.

- Resource based policies : These are inline policies directly applied on the resource that has to be accessed from same/other accounts. This is mainly used for cross-account resource access

Policy versioning: Customer managed policies can normally have only 5 versions being managed at a single point of time. This is useful when you make a change to a policy and it breaks something, you can quickly set the default setting to a previously used policy

IAM Roles are more preferred instead of resource based policies which are not extendable to other entities


![image](https://user-images.githubusercontent.com/42945500/145450429-98226093-9094-421b-8625-824bc504907a.png)
![image](https://user-images.githubusercontent.com/42945500/145450436-ec989729-0455-4734-aad5-9bbd32375252.png)
![image](https://user-images.githubusercontent.com/42945500/145450448-7f08be2d-ec13-4cf0-89c6-22ba55ec3206.png)
![image](https://user-images.githubusercontent.com/42945500/145450556-46526ca8-6a36-4e3f-a9c2-9f5458947bb5.png)
![image](https://user-images.githubusercontent.com/42945500/145450570-c7cee1fd-f494-4f5c-8a35-de8e6c04e6bc.png)
