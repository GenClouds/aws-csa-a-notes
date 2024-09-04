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

