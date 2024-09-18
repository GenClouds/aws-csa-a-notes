# Kubernetes Components

## Control Panel
- **Managed**: Control panel managed.
- **Function**: Runs containers inside.

## Kubelet
- **Function**: Interacts with the control plane.

## Pods
- **Description**: Contains one or more containers, a single unit of compute.

## Cluster
- **Description**: Combination of nodes.

## Nodes
- **Description**: A physical server that functions as a worker.

## etcd
- **Description**: A server used for backing store. It uses the cluster and nodes to communicate with each other for scaling.

## API
- **Function**: Runs inside a control plane.

## Scheduler
- **Function**: Identifies the pods that do not have a node assigned.

## Cloud Controller Manager
- **Function**: Links Kubernetes to different cloud platforms.

## Proxy
- **Function**: Network proxy.

# Restrict View Access
- **Description**: Restricting the behavior overall from caching requests.

# SSL
- **Function**: Used as encryption in transit.
- **Certificate**: Generated and imported from ACM.
- **Domain**: When we have a domain with cloudfront.com, SSL is already supported.
- **Alternate Domain**: When we want to alternate the domain CNAME, we get an endpoint by name to access this with HTTPS. We need an SSL certificate.
- **Note**: SSL certificates are digitally signed by an authorized and trusted entity. SSL will always be regionally locked.
- **Support**: Supported with ELB and CloudFront. Does not support S3.

# TLS
- **Function**: Encrypted part of HTTP.
- **Validation**: Allows a web server to validate its identity.
- **Limitation**: It is impossible to host multiple HTTPS on a single IP.
- **Extension**: TLS extension SNI (Server Name Indication) gives the ability to the user to tell the server which domain name it is attempting to access.

# DynamoDB

## Overview
- **Type**: NoSQL
- **Orientation**: Document-oriented, wide column.
- **Nature**: Serverless database.
- **Features**: Fast, scalable, flexible.

## Local Secondary Indexes (LSI)
- **Function**: Allows us to create an alternative table using an alternative sort key.
- **Creation**: Can be created with the table.
- **Limit**: 5 LSI per base table.
- **Capacity**: Has its own RCU and WCU.

## Global Secondary Indexes (GSI)
- **Function**: Creates an alternative table using different sort key and partition key.
- **Creation**: Can be created any time.
- **Limit**: 20 GSI per base table.
- **Capacity**: Has its own RCU and WCU.

## Stream
- **Description**: Time-ordered list of items in a table. Every time changes occur (update, delete, insert), it gets listed.
- **Lambda Triggers**: When item changes event occurs, the event contains data which then triggers by Lambda.
- **Use Cases**: Reporting and analytics, aggregation, messaging, etc.

## DynamoDB Global
- **Function**: Multi-cross region replication.
- **Performance**: Sub-second replication between replicated tables.
- **Operations**: Read and write operations.
- **Features**: High availability and auto-scalable.

## DynamoDB Accelerator (DAX)
- **Type**: In-memory cache for DynamoDB.
- **Integration**: Integration between cache and DB.
- **Benefits**: Less complexity for developers, less overhead for admin, scale out and up, high availability and scalable.
- **Use Cases**: High sales availability, more read workload, reading or load retrieval issues.
- **Example**: Application directly retrieves data from DynamoDB by placing DAX. If the data is available, it is a cache hit; if not, it returns and caches back.

## DB TTL
- **Function**: Timestamp + value. Item gets deleted at a certain time.
- **Enable**: Enable TTL on table and choose attribute with value in seconds.

# Amazon Athena
- **Type**: Serverless interactive query service.
- **Data**: Stored in S3 and you can perform ad-hoc queries.
- **Billing**: Per query.
- **Function**: Translates the data into table schema. Output given to other services.
- **Exam Points**: No infrastructure in advance, no schema in advance.

# ElastiCache Product
- **Type**: In-memory database, high performance.
- **Engines**: Redis, Memcached.
- **Function**: Used to cache the data.
- **Use Case**: Heavy read workload with low latency.
