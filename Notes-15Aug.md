# VPC - Virtual Private Cloud (Basic) 🚀

A private environment where private resources are deployed.

## Overview

In a hybrid environment, VPC is a service that connects a private network to an on-premises network. While creating multi-cloud deployments, VPC lets you connect to other cloud platforms.

### Key Points

- **VPC**: A virtual private network inside AWS.
- **Regional Resilient Service**: VPCs are resilient within a region.
- **Single Account and Region**: A VPC is within one account and one region.
- **Multiple AZs**: Operates from multiple Availability Zones (AZs) in a specific region.
- **Isolation**: By default, a VPC is isolated and private unless configured otherwise.

## Types of VPCs

Inside regions, we have two types of VPCs:

1. **Default VPC**
2. **Custom VPC**

### Differences Between Default and Custom VPCs

| Feature                | Default VPC                          | Custom VPC                          |
|------------------------|--------------------------------------|-------------------------------------|
| **Number per Region**  | One                                  | Many                                |
| **Configuration**      | Pre-configured by AWS                | Configurable by user                |
| **Purpose**            | Demo and testing                     | AWS deployments                     |
| **Flexibility**        | Less flexible                        | Highly flexible                     |
| **Communication**      | Limited                              | Can communicate with others         |
| **IP Address Range**   | Always 172.31.0.0/16                 | Multiple CIDR ranges                |
| **Subnets**            | Pre-configured subnets in each AZ    | Custom subnets in each AZ           |
| **Internet Gateway**   | Default IGW                          | Custom IGW                          |
| **NACL**               | Default NACL                         | Custom NACL                         |
| **Public IP**          | Assigned by default                  | Configurable                        |

### Default VPC

- **One VPC per region**
- **Pre-configured by AWS**
- **Used for demo and testing purposes**
- **Configuration handled by AWS**
- **Less flexible**

### Custom VPC

- **Many VPCs per region**
- **Customizable**: Configure them in any way under the rules and limits.
- **Communication**: Able to communicate with others.
- **Private by default**: 100% private by default.
- **Mostly used for AWS deployments**

## VPCs are Regional Resilient 🌍

Every VPC is allocated a range of IP addresses called VPC CIDR.

### CIDR - Classless Inter-Domain Routing

- Defines the start and end of IP addresses that VPCs use.
- Anything inside VPC uses the CIDR range for communication and outgoing connections.
- **Custom VPC**: Multiple VPC CIDR ranges.
- **Default VPC**: Only one CIDR range, always 172.31.0.0/16.

## Subnets

A VPC network is subdivided into sub-networks called subnets. Each subnet is located inside one Availability Zone (AZ).

- **Default VPC**: Pre-configured subnets in each AZ, falling under VPC CIDR.
- **Custom VPC**: Custom subnets in each AZ, using VPC's range of IP addresses.

### Notes

- IP addresses cannot overlap between subnets.

## Default VPC Facts

- **One per region**
- **Can be removed, recreated, deleted**

### Weaknesses

- Always 172.16.0.0/16, not enough for production deployments.
- /20 subnet created in each AZ in the region.

### CIDR Range

- Smaller the CIDR, higher the network range.
- Larger the CIDR range, smaller the network range.
- Example: Two /17 fit into /16.

## Default VPC Components

- **Default IGW (Internet Gateway)**
- **Default NACL (Network ACL)**
- **Public IPv4 Addresses**: Assigned by default.

