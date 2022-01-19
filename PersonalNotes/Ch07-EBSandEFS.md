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


![image](https://user-images.githubusercontent.com/42945500/145621611-2b059e1d-f380-43bb-a3d9-adf59bb0b4b4.png)
![image](https://user-images.githubusercontent.com/42945500/145621625-d9994511-d026-48da-9552-df2ac3539406.png)
![image](https://user-images.githubusercontent.com/42945500/145621652-d3e7aeab-dff3-4787-83c0-46cb245a38b5.png)
![image](https://user-images.githubusercontent.com/42945500/145621682-d1586b49-0d0c-415e-8fd2-a686b28ebd89.png)
![image](https://user-images.githubusercontent.com/42945500/145621839-5873b0c3-2667-4eb2-b4bd-3a4340d5c919.png)
![image](https://user-images.githubusercontent.com/42945500/145621905-01d2f884-523e-4321-a5f0-1b85cd92fdba.png)
![image](https://user-images.githubusercontent.com/42945500/145621948-58f31055-3f9b-459c-8bd2-1b69c82a02c3.png)
![image](https://user-images.githubusercontent.com/42945500/145622031-5ce35e8c-574d-4876-8677-6407acdcb89c.png)
![image](https://user-images.githubusercontent.com/42945500/145622139-140a2626-9e0f-4d36-9e6f-759cb86dd37f.png)
![image](https://user-images.githubusercontent.com/42945500/145622238-1a7ea446-04a7-4805-be04-3566e94b3b06.png)
![image](https://user-images.githubusercontent.com/42945500/145622385-769facaa-0039-4d55-8812-14b2c942b601.png)
![image](https://user-images.githubusercontent.com/42945500/145622467-e5cd1c4c-3ce5-482d-882c-e75030afa9b5.png)





