# Storage Terms and Types

## Storage Terms

1. **Direct Storage**: Directly attached to the device, like instance store to EC2. It is superfast in performance but can cause problems if hardware fails or if the device moves between hosts.
2. **Network Attached Storage**: High resilient storage. Create volume and then attach to the device, like EBS to EC2.
3. **Ephemeral Storage**: Temporary storage, e.g., instance storage where data storage is not persistent.
4. **Persistent Storage**: Permanent storage like EBS Volume.

## Storage Types: Presentation and Usage

1. **Block Storage**:
   - Create volume and present a collection of blocks to the OS.
   - The OS then creates files like NTFS or EXT and mounts it.
   - The structure is in the form of hard disks, SSDs, or physical media. However, they have no built-in structure.
   - Bootable and mountable.

2. **File Storage**:
   - It has a proper structure. File servers provide ready-made files, allowing browsing and creating folders to store collections of files.
   - Presented to the OS as a file share.
   - Not bootable.
   - Mountable.

3. **Object Storage**:
   - It has no structure. It just stores collections of objects.
   - Presented in the form of a flat object.
   - Not bootable.
   - Not mountable.
   - The main benefit is super scalability, allowing thousands of people to access and read/write to it.

## Storage Performance

| STORAGE Type | IOPS | THROUGHPUT |
|--------------|------|------------|
| Block size * IOPS = THROUGHPUT |
| 64KB * 100 IOPS = 6.4 MB/s |
