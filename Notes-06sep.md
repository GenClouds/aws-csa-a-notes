# EBS Volume Types

Amazon EBS provides various volume types, each with different performance characteristics and pricing, allowing you to tailor your storage to your application's needs.

## Solid State Drive (SSD) Volumes

### General Purpose SSD (gp3)

- **Use Cases**: Transactional workloads, virtual desktops, medium-sized single-instance databases, boot volumes, development, and test environments.
- **Performance**: Balances price and performance for most applications.
- **Max IOPS**: 16,000
- **Max Throughput**: 1,000 MiB/s
- **Volume Size**: 1 GiB - 16 TiB

### Provisioned IOPS SSD (io2)

- **Use Cases**: I/O-intensive database workloads, applications requiring sustained IOPS performance, low-latency interactive applications.
- **Performance**: High performance with sub-millisecond latency.
- **Max IOPS**: 64,000
- **Max Throughput**: 1,000 MiB/s
- **Volume Size**: 4 GiB - 16 TiB

## Hard Disk Drive (HDD) Volumes

### Throughput Optimized HDD (st1)

- **Use Cases**: Big data, data warehouses, log processing.
- **Performance**: Optimized for large, sequential workloads.
- **Max Throughput**: 500 MiB/s
- **Volume Size**: 500 GiB - 16 TiB

### Cold HDD (sc1)

- **Use Cases**: Infrequently accessed data, scenarios where the lowest storage cost is important.
- **Performance**: Lowest cost HDD volume.
- **Max Throughput**: 250 MiB/s
- **Volume Size**: 500 GiB - 16 TiB

## Previous Generation Volumes

### Magnetic (standard)

- **Use Cases**: Workloads where data is infrequently accessed.
- **Performance**: Previous generation, lower performance.
- **Max Throughput**: 40-90 MiB/s
- **Volume Size**: 1 GiB - 1 TiB

