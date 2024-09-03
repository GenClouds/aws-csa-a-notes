# 🔒 Object Encryption

## Client-Side Encryption
- **Client-side encryption**: The objects being uploaded are encrypted by the client before they leave. This means the data is in ciphertext all the time.

## Server-Side Encryption
- **Server-side encryption**: Even though the data is encrypted in transit using HTTPS, the objects themselves are not initially encrypted. 

Both methods ensure that if somebody were to get the physical disks from AWS where your data is stored, they would need a key to access the data.

### Differences
- **Client-side encryption**: Everything is in our control. We own the data, generate the key, and manage the key.
- **Server-side encryption**: The encryption is managed by the server.

## Types of Server-Side Encryption (SSE)
1. **SSE-C**: Server-side encryption with customer-provided keys. Full control and visibility.
2. **SSE-S3**: Server-side encryption with AWS S3-managed keys (default). Uses strong algorithm AES-256, less admin overhead.
3. **SSE-KMS**: Server-side encryption with AWS Key Management Service. Best for granular control, logging, and benefits of role separation.

## Encryption and Decryption Process
At a higher level, SSE involves two components: encryption and decryption processes.

1. **Encryption**: Takes plaintext, attaches a key, applies an algorithm, and creates ciphertext.
2. **Decryption**: Takes ciphertext, applies a key and algorithm, and generates plaintext.

It is a symmetrical encryption, meaning the same key is used for both encryption and decryption.

!Encryption Process
