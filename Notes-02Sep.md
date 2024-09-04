# S3 Lifecycle Configuration

A set of rules that apply actions on a bucket or a group of buckets.

## Types of Actions

### 1. Transition Action
This action changes the storage class of an object. Examples include:
- Transitioning an object from Standard S3 to Infrequent Access (IA) after 30 days.
- Transitioning an object from IA to Glacier Deep Archive after 180 days.

### 2. Expiration Action
This action deletes the bucket, buckets, or versions. It helps to keep the bucket tidy by expiring objects.

## Versioning
Both actions are also applied to versioning if enabled.

## Storage Transition Model
All the storages follow a waterfall model. The transitions between them are mentioned in the picture as well.


![Screenshot 2024-09-04 135319](https://github.com/user-attachments/assets/d3a6e585-c4bd-45f9-bf2e-cc78da289fd7)


# S3 Replication

Replication is done between a source bucket and a destination bucket.

## Types of Replication

### 1. Cross Region Replication (CRR)
- The object is replicated across multiple and different regions.

### 2. Same Region Replication (SRR)
- The bucket within the object is replicated in the same region.

## Replication Time Control (RTC)
- RTC guarantees replication within 15 minutes as per SLA.
- Provides enhanced monitoring capabilities.

## What is Replicated
- Objects, including prefixes and tags.
- Storage class must be the same for both source and destination.
- Ownership of the bucket is replicated from source to destination.

## Important Considerations
- By default, replication is not retroactive and versioning is enabled.
- If replication is enabled, only the bucket will be replicated, not the objects inside. To replicate existing objects, versioning must be enabled.
- By default, replication is one-way, but it can be configured for bidirectional replication.
- Handles unencrypted objects, SSE-S3, and SSE-KMS, but requires extra configuration for SSE-C.
- Glacier and Glacier Archive are not replicated.

## Why Use Replication

### Same Region Replication
- Log aggregation.
- PROD and TEST sync.

### Cross Region Replication
- When strict sovereignty is not required.
- Global resilience improvements.
- Provides low latency.


