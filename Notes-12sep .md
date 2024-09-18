# Presigned URLs

Presigned URLs allow a person to access an object in a bucket. 

To access the object inside a bucket, an identity or authentication is usually required. However, with a presigned URL, private objects can be accessed without authentication. An IAM admin user requests the S3 bucket with some access permission policies, and S3 generates the presigned URLs including bucket ID, name, expiry, and details about the bucket and the object. The IAM user then passes this URL to an anonymous user to access the specific object with get, put, and download permissions for a short time until it expires.

## Example Use Case:
- We can create a URL for an object which we don't have direct access to.
- The permissions should match the identity we generated.
- Do not generate presigned URLs with roles.

# Bastion Host

Bastion hosts and jumpboxes are the same. They provide a way to access the VPC. 

A bastion host allows incoming management connections to the VPC and, once connected, allows access internally. It serves as an entry point for private-only VPCs. Configuring a bastion host involves allowing certain IP addresses to SSH into the server.

# Stateless Firewalls

Stateless firewalls do not know the state of connections, meaning they see both requests and responses to the server and think in terms of inbound/outbound rules. This creates an overhead as two rules are needed for one connection.

For reverse connections, it is also difficult to know the state. Stateless firewalls use ephemeral temporary ports for connections. The connection where initiated and responded always has an inverse rule.

# Stateful Firewalls

Stateful firewalls are intelligent and identify connections, meaning both requests and responses. Generally, we have to allow the request or not, and the response is allowed or not automatically. This reduces admin overhead. Stateful firewalls know the ports to make connections and are expected to make fewer mistakes.

# NACL vs Security Group

- **NACL** is stateless, while **SG** is stateful.
- NACL looks at requests and responses separately, while SG has two rules: allow or deny requests and automatically detect responses.
- NACL has explicit allow and deny rules, while SG has only explicit allows.
- NACL is not connected to logical resources, while SGs are connected.
- Note that SGs are not connected to instances; they are connected to ENIs (Elastic Network Interfaces).

# Virtualization

- **Para-virtualization**
- **Emulated virtualization** (hardware + virtualization)

Hardware-assisted virtualization, also known as SR-IOV (Single Root I/O Virtualization), shows a single NIC card as many mini NICs.

## EC2 is good for:
- Traditional application compute needs.
- Long-running compute.
- Server-style applications (applications waiting for requests).
- Applications requiring burst and steady-state performance.
- Monolithic application stacks.
- Migrating application workloads and disaster recovery.



