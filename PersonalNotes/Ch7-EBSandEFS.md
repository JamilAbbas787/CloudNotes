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

## Snapshots
- Snapshots exist on S3
- Incremental
- Can only be shared in the region they were created

