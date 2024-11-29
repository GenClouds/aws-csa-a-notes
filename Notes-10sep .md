# Storage Terms

1. **Direct Storage**: Directly attached to the device, like instance store to EC2. It is superfast in performance but can cause problems if hardware fails or if the device moves between hosts.
2. **Network Attached Storage**: High resilient storage. Create volume and then attach to the device, like EBS to EC2.
3. **Ephemeral Storage**: Temporary storage, e.g., instance storage where data storage is not persistent.
4. **Persistent Storage**: Permanent storage like EBS Volume.

# Storage Types: Presentation and Usage

1. **Block Storage**:
   - Create volume and present a collection of blocks to the OS.
   - The OS then creates files like NTFS or EXT and mounts it.
   - The structure is in the form of hard disks, SSDs, or physical media. However, they have no built-in structure.
   - Bootable and mountable.

2. **File Storage**:
   - It has a proper structure. File servers provide ready-made files, allowing users to browse and create folders to store collections of files.
   - Presented to the OS as a file share.
   - Not bootable.
   - Mountable.

3. **Object Storage**:
   - It has no structure. It just stores collections of objects.
   - Presented in the form of a flat object.
   - Not bootable.
   - Not mountable.
   - The main benefit is super scalability, allowing thousands of people to access and read/write to it.

# Storage Performance

| STORAGE Type | IOPS | THROUGHPUT |
|--------------|------|------------|
| Block Size   | IOPS | THROUGHPUT |
| 64KB * 100 IOPS = 6.4 MB/s |

## General Purpose SSD

- It creates volume with IO credit. If there is no credit, there will be no operations.
- Assume a minimum of 1GB and a maximum of 16TB of IOPS.
- Great for booting and initial workload.
- If we have a 160KB file to transfer, it makes 10 blocks of 10 IO credits.
- If the load is unbalanced and not constant, it bursts from 3 IOPS per GB to 3000 IOPS.
- Good for general usage.

## GP3 vs GP2

- GP3 is replacing GP2 because it is more cost-effective.
- GP3 removed the credit bucket architecture.
- Minimum volume size ranges from 3000 KB/s to a maximum of 124 MB/s.
- Extra cost for 16000 IOPS and 1GB.
- 4x maximum throughput than GP2, like 1000 MB/s.

# EBS Snapshots

- EBS Snapshots are backups of data consumed within EBS Volumes - Stored on S3.
- Snapshots are incremental, the first being a full backup, and any future snapshots being incremental.
- Snapshots can be used to migrate data to different availability zones in a region or to different regions of AWS.
- This lesson steps through the theory and architecture of EBS Snapshots.

# Containers and Pods

- Just like we host containers on EC2 in ECS, we have pods hosted on nodes.
- Just like we have EC2 mode and Fargate mode in ECS, we have self-managed pods, managed pod groups, and Fargate pods.
