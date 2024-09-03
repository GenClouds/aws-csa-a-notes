## Key Management Service (KMS)

**KMS** is a regional and public service integrated with other AWS services to provide encryption capabilities. It allows you to create, store, and manage cryptographic keys.

### Cryptographic Key
- A key used to convert plaintext to ciphertext and vice versa.
- Handles both symmetric and asymmetric keys.
- Performs cryptographic operations like encryption and decryption.
- Keys never leave KMS, providing **FIPS 140-2 Level 2** compliance.
- KMS keys are logical entities defined by attributes like ID, date, description, policy, and state.
- These keys are backed by physical key materials used to encrypt and decrypt data.
- KMS keys can be used to encrypt or decrypt data up to **4KB** in size.

KMS provides granular permissions, requiring specific permissions for each individual operation.

### Data Encryption Keys (DEKs)

- DEKs are generated using KMS keys and are used to encrypt and decrypt data larger than 4KB.
- **Important**: KMS does not store DEKs.
- When DEKs are generated, two versions are created:
  - **Plaintext Version**
  - **Ciphertext Version**
- To decrypt data, the encrypted data, along with the encryption key, is passed back to KMS, which uses the same key to decrypt it.
- Services like S3 generate data encryption keys for objects using KMS.

### Types of KMS Keys
- **Customer-Owned Keys**:
  - **Customer Managed Keys**: Fully managed and controlled by the customer.
  - **AWS Managed Keys**: Managed by AWS, with less control by the customer.
- **AWS-Owned Keys**: Managed entirely by AWS, with no direct customer access.

![Screenshot 2024-09-03 154617](https://github.com/user-attachments/assets/91ddb8a2-6afd-49e8-8625-7ba61c6ff43f)
