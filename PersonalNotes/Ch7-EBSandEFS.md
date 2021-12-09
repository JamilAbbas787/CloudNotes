# CHAPTER 7 - Elastic Block Storage (EBS) and Elastic File System (EFS)

## EBS
### Volume Types
#### Solid State Drives
- General Purpose (GP2 and GP3)
  - Suitable for boot disks
  - Up 16,000 Iops
  - 99.9% durability
- Provisioned IOPS SSD (io1 and io2)
  - High Performance
  - Greater than 16,000 IOPS
  - Suitable for OLTP
#### Hard Drive
- Throughput Optimized HDD (st1)
  - Big data, data warehouse, ETL, log processing
  - Cannot be a boot volume
  - 500 mb/s
- Cold HDD (sc1)
  - Low Cost Option
  - Less frequently accessed data
  - Cannot be a boot volume

___

### Snapshots
- Snapshots exist on S3
- Incremental
- Can only be shared in the region they were created
 
___

## EFS
- NFSv4
- Pay per use
- Mange Network file system that can be mounted EC2 instances
- Basically shared storage for EC2 instances across Availability Zones
- Scales automacticly; Don't need to select size like EBS

### Performance
- General Purpose
  - Content Management
- Max I/O
    - Big Data

### Storage Tiers
- Standard
- Infrequently Acessed
___

## FSx
- Microsoft Windows file system
### FSx for Lesture
- Processes datasets, AI, achine Learning 

### AMI
Amazon Machine Image
- Region
- Operation system
- Architecture (32 v 64 bit)
- Launch Permissions
- Storage for the root device (root device volume)



