# Chapter 3 - AWS Fundamentals

## Regions / Availability Zones (AZs)

_____

- Regions
  - AWS Geographical regions like US East, US West, EU Central etc

- Availability Zones
  - Distinct data centres that host the physical compute and other resources for AWS
  - AWS ensures a minimum of 2 AZs per region. They are often separated with each other but a geographical calamity could still impact/disrupt services on both

- Edge Locations
  - Each Region further consists of many edge locations
  - They serve cached data for frequent access from nearby users
  - Edge location can also be used to write data (For eg. in S3 Transfer Acceleration)

- As of today there are approximately 15 regions, 45 AZs and ~100+ Edge locations fronted by Cloudfront.
- Sometimes edge locations could also be operated/managed by AWS partner network

## Who owns what in the cloud?

_____

User

- Security groups
- IAM Users
- Patching EC2 operating systems
- Patching databases running on EC2

AWS

- Data Centers
- Security Cameras
- Cabling
- Patching RDS operating systems

![image](https://user-images.githubusercontent.com/42945500/145450180-5c37978c-c1e5-4a13-9619-ea5c450da257.png)
![image](https://user-images.githubusercontent.com/42945500/145450212-4deb8168-6730-4dc5-b2f2-bf061a1a96cc.png)
![image](https://user-images.githubusercontent.com/42945500/145450234-c8e05180-f71f-4871-ae90-79828ca0f458.png)
