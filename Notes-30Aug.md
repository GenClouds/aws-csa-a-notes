# Object Versioning

### Overview
Versioning allows us to store multiple versions of objects within buckets. When an object is modified, the old version is replaced and a new version is created.

### Key Points
- **Versioning Behavior**:
  - Once versioning is enabled, it cannot be disabled but can be suspended. If desired, it can be re-enabled.
  - All versions of an object consume storage space, and you are billed for all versions.

- **Object Identification**:
  - Each object has an attribute called `ID`. An object without versioning enabled has an `ID` of `0`.
  - By default, accessing an S3 bucket object without specifying a version returns the latest version. However, you can request a specific version by using its `ID`.

- **Object Deletion**:
  - If an object with versioning enabled is deleted, a "delete marker" version is created. This marker hides the object, making it appear as if it has been deleted.
  - Deleting the "delete marker" restores the object to its previous state.
  - Specific versions of an object can be deleted if necessary.

---

# MFA Delete

### Overview
- **MFA Delete** is a feature that can be enabled in the versioning configuration of a bucket.
- **MFA (Multi-Factor Authentication)** is required to:
  - Change the bucket's versioning state.
  - Delete a version of an object.







# S3 Performance Optimization

### Single PUT Upload
> For transferring data between two points, AWS uses a data transfer protocol called **BitTorrent** to provide speedy data transfer.

- **AWS Limitation**: Each part of the upload is limited to a maximum of 5GB.

### Multi-Part Upload
Multi-Part Upload improves the speed and reliability of uploading data to S3 by breaking data into individual blobs.

- **Minimum Data Size**: 100MB
- **Maximum Number of Parts**: 10,000
- **Part Size Range**: 5MB to 5GB
- **Resilience**: Parts can fail and be restarted in isolation without affecting the entire upload.

### S3 Accelerated Transfer
S3 Accelerated Transfer uses AWS's global network of edge locations to speed up uploads.

- **Requirements**:
  1. The bucket name cannot contain periods.
  2. The bucket name needs to be DNS-compatible.

By enabling accelerated transfer, your data is first delivered to the closest, high-performance edge location, which then connects to S3. This ensures a **flexible**, **faster**, and **consistent** low-latency experience.



