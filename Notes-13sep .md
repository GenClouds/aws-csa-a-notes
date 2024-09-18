# AWS S3 Replication

## Types of Replication

1. **Cross-Region Replication (CRR)**: The object is replicated across multiple and different regions.
2. **Same-Region Replication (SRR)**: The bucket within the object is replicated in the same region.

## Replication Time Control (RTC)
- **Feature**: Guarantees replication within 15 minutes as per SLA.
- **Monitoring**: Provides more monitoring sources with SLA.

## What is Replicated
- **Objects**: Including prefixes and tags.
- **Storage Class**: Should be the same for both source and destination.
- **Ownership**: The bucket ownership is replicated from source to destination.

## Important Considerations
- **Non-Retroactive**: By default, replication is not retroactive and versioning is enabled.
- **Versioning**: To replicate existing objects, versioning must be enabled.
- **One-Way Replication**: By default, but can be configured for bidirectional replication.
- **Encryption Handling**: Handles unencrypted, SSE-S3, and SSE-KMS, but requires extra configuration for SSE-C.
- **Glacier**: Glacier and Glacier Archive are not replicated.

## Why Use Replication

### Same-Region Replication (SRR)
- **Log Aggregation**: Useful for aggregating logs.
- **PROD and TEST Sync**: Synchronize production and test environments.
- **Sovereignty**: Used when strict sovereignty is not required.

### Cross-Region Replication (CRR)
- **Global Resilience**: Improves global resilience.
- **Low Latency**: Provides low latency.

## Example Use Cases
- **Log Aggregation**: Aggregating logs within the same region.
- **PROD and TEST Sync**: Synchronizing production and test environments.
- **Global Resilience**: Enhancing global resilience by replicating across regions.
- **Low Latency**: Ensuring low latency access to data.

## Additional Notes
- **Replication Time Control (RTC)**: Ensures replication within 15 minutes.
- **Monitoring**: Enhanced monitoring capabilities with SLA.
- **Encryption**: Supports unencrypted, SSE-S3, and SSE-KMS with additional configuration for SSE-C.
- **Non-Retroactive**: Replication is not retroactive by default; versioning must be enabled to replicate existing objects.
- **One-Way Replication**: Default setting, but can be configured for bidirectional replication.
- **Glacier**: Glacier and Glacier Archive are not replicated.

