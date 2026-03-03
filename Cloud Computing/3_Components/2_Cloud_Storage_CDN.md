# Cloud Storage and CDN

This document describes common cloud storage types (Direct Attached, File, Block, Object) and Content Delivery Networks (CDNs). It covers characteristics, performance, use cases, cost considerations, and resilience.

---

## Storage Types Overview

Cloud storage generally falls into four categories:

- **Direct Attached (Local) Storage:** Fast and local to a server, but ephemeral and not shareable.
- **File Storage:** Shared file systems (e.g., NFS) mounted over a network; suitable for concurrent access.
- **Block Storage:** Low-latency volumes presented to compute nodes; ideal for databases and performance-sensitive workloads.
- **Object Storage:** API-accessed, highly scalable storage for unstructured data (buckets/objects).

---

## Direct Attached Storage

Overview

- Storage presented directly to a cloud server (inside host chassis or same rack). Fast and low-latency but typically ephemeral and not shareable across nodes.

When to use

- Temporary local caching, scratch disks for compute jobs, high-performance local processing where persistence across hosts is not required.

---

## File Storage

Overview

- File storage is typically presented via a network file system (NFS) and mounted on compute nodes over Ethernet. It supports concurrent access by multiple nodes.

Performance and networking

- Accessed over Ethernet; speeds can vary based on network and load. Use when consistent high IOPS/low latency is not critical.
- Subnetting, ACLs, and security groups provide protection at network and instance levels.

Use cases

- Shared home directories, departmental file shares, content repositories, and collaborative applications.

Cost and limitations

- Cost-effective for shared access but may not meet requirements for high-performance databases.

---

## Block Storage

Overview

- Block storage exposes volumes to a compute node and typically uses high-performance networks (e.g., fiber) to deliver low-latency access. Data is organized in blocks and mounted as a volume.

Performance

- Designed for high IOPS and low latency. Important metric: IOPS (Input/Output Operations Per Second).

Use cases

- Databases, transactional systems, and other performance-sensitive workloads.

Cost and characteristics

- Generally more expensive than file storage due to specialized infrastructure and performance guarantees.

---

## Object Storage

Overview

- Object storage stores data as objects in flat namespaces (buckets). It is accessed via APIs (commonly S3-compatible) and does not require attachment to compute nodes.

Characteristics

- Highly scalable, cost-effective for large volumes of unstructured data, and supports metadata per object.
- Typical tiers: Standard (frequent access), Infrequent/Cold (lower cost), Vault/Archive (very low cost, slower retrieval).

Performance and access

- Slower than block or file storage for small, frequent reads/writes; some archive tiers can take hours to retrieve.

Use cases

- Backups, media assets, large datasets, analytics data lakes, and static website hosting.

Cost model

- Priced per gigabyte stored plus request and retrieval costs for certain tiers. Lifecycle rules can automatically transition objects between tiers.

---

## Comparison and Choosing Storage

- **Performance-sensitive / low-latency:** Block storage.
- **Shared access / file semantics:** File storage.
- **Large-scale, unstructured data / archival:** Object storage.
- **Local, ephemeral high-performance needs:** Direct attached storage.

Consider encryption at rest/in transit, access controls, data residency, and resilience requirements when choosing a storage type.

---

## Content Delivery Networks (CDN)

Overview

- A CDN is a distributed network of edge servers that cache and deliver content based on the user's geographic location to reduce latency and origin load.

Benefits

- Speed improvement by reducing physical distance between users and content.
- Reduced origin server load and improved availability.

Security and UX

- CDNs can improve security (DDoS mitigation, TLS termination, WAF features) and provide a better user experience via faster load times.

Cost considerations

- Costs depend on bandwidth, request volume, cache hit ratios, and geographic egress charges. Evaluate storage size, access frequency, and caching strategy.

Use cases

- Static website assets, media streaming, software distribution, and API acceleration.

---

## Summary

Choose storage based on performance, access patterns, cost, and resilience. Use CDNs to accelerate delivery and reduce origin load for globally distributed audiences.
