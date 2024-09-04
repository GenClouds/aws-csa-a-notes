# Presigned URLs

Presigned URLs allow a person to access an object in an S3 bucket without requiring authentication.

## How It Works

Typically, accessing an object inside a bucket requires identity or authentication. However, with presigned URLs, you can access private objects without authentication.

### Steps to Generate Presigned URLs

1. An IAM admin user requests a presigned URL from the S3 bucket with the necessary permissions.
2. S3 generates the presigned URL, which includes:
   - Bucket ID
   - Bucket name
   - Expiry time
   - Information about the bucket and the object

3. The IAM user can then share this URL with an anonymous user, allowing them to access the specific object with GET, PUT, and download permissions for a short time until the URL expires.

## Important Considerations

- You can create a URL for an object even if you don't have direct access to it, as long as the permissions match the identity used to generate the URL.
- Do not generate presigned URLs with roles.


- **Exams Hand-Up**: Share URLs for objects that users don't have direct access to, ensuring permissions are correctly matched.
- **Temporary Access**: Provide temporary access to private objects without exposing your credentials.

By using presigned URLs, you can securely and temporarily grant access to your S3 objects, making it a versatile tool for various scenarios.
