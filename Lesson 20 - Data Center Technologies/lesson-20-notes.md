# Lesson 20: Data Center Technologies

- Topics to be covered in this lesson:
  - Brief and high-level overview of challenges and technologies facing data centers
  - **Goal**: provide context for mechanisms from previous lessons
  - Multi-tier architectures for internet services
  - Cloud computing
  - Cloud and _big data_ technologies

## Internet Services

- **Internet service**: any type of service provided via web interface
- **Presentation**: static content
- **Business logic**: dynamic content
- **Database tier**: data store
  - Not necessarily separate processes on separate machines
  - Many available open source and proprietary technologies
- **Middleware**: supporting, integrative or value-added software technologies
  - In multi-process configurations: some form of IPC used, including RPC/RMI, shared memory, etc.

## Internet Service Architectures

- For scale: multi-process, multi-node (_scale out_ architecture)
  1. _Boss-worker_: front-end distributes requests to nodes
  2. _All equal_: all nodes execute any possible step in request processing, for any request (functionally homogeneous)
  3. _Specialized nodes_: nodes execute some specific step(s) in request processing for some request type (functionally heterogeneous)

## Homogeneous Architectures

- **Functionally homogeneous**:
  - Each node can do any processing step
  - Pros:
    - Keeps front-end simple
    - Does not mean that each node has all data, just each node can get to all data
  - Cons:
    - How to benefit from caching?

## Heterogeneous Architectures

- **Functionally heterogeneous**:
  - Different nodes, different tasks/requests
  - Data does not have to be uniformly accessible everywhere
  - Pros:
    - Benefit of locality and caching
  - Cons:
    - More complex front-end
    - More complex management

## Cloud Computing Requirements

- **Traditional approach**:
  - Buy and configure resources: determine capacity based on expected demand (peak)
  - When demand exceeds capacity:
    - Dropped requests
    - Lost opportunity
- **Ideal cloud**:
  - Pros:
    - Capacity scales elastically with demand
    - Scaling instantaneous, both up and down
      - Cost is proportional to demand, to revenue opportunity
    - All of this happens automatically, no need for hacking wizardry
    - Can access anytime, anywhere
  - Cons:
    - Don't _own_ resources
- **Cloud computing requirements** (summarized):
  - On-demand, elastic resources and services
  - Fine-grained pricing based on usage
  - Professionally managed and hosted
  - API-based access

## Cloud Computing Overview

- **Shared resources**:
  - Infrastructure and software/services
- **APIs for access and configuration**:
  - Web-based, libraries, command line, etc.
- **Billing/accounting services**:
  - Many models: spot, reservation, entire marketplace
  - Typically discrete quantities: tiny, medium, x-large, etc.
- **Managed by cloud provider**

## Why Does Cloud Computing Work?

- **Law of large numbers**:
  - Per customer there is large variation in resource needs
  - Average across many customers is roughly constant
- **Economies of scale**:
  - Unit cost of providing resources or service drops at _bulk_

## Cloud Computing Vision

> If computers of the kind I have advocated become computers of the future, then computing many some day be organized as a public utility, just as the telephone system is a public utility... The computer utility could become the basis of a new and important industry. (_John McCarthy, MIT Centennial, 1961_)

- Computing: fungible utility
- Limitations exist: API lock-in, hardware dependence, latency, privacy, security, etc.

## Cloud Deployment Models

- **Public**: third-party customers/tenants
- **Private**: leverage technology internally
- **Hybrid (public + private)**: fail over, dealing with spikes, testing
- **Community**: used by certain type of users

## Cloud Service Models

- **On-premise**:
  - You must manage all components and services
- **IaaS (Infrastructure as a Service)**:
  - You manage components such as applications, data, run-time, middleware, OS
  - Others manage virtualization, servers, storage, and networking
- **PaaS (Platform as a Service)**:
  - You manage components such as applications and data
  - Others manage run-time, middleware, OS, virtualization, servers, storage, and networking
- **SaaS (Software as a Service)**:
  - Opposite of on-premise, others manage all components and services

## Requirements for the Cloud

1. _Fungible_ resources
2. Elastic, dynamic resource allocation methods
3. Scale: management at scale, scalable resources allocations
4. Dealing with failures
5. Multi-tenancy: performance and isolation
6. Security

## Cloud Enabling Technologies

- **Virtualization**:
  - Resource provisioning (scheduling)
- **Big data** processing (Hadoop MapReduce, Spark, etc.)
- Storage:
  - Distributed front-end (_append only_)
  - NoSQL, distributed in-memory caches
- Software-defined networking, storage, data centers, etc.
- Monitoring: real-time log processing (e.g., AWS CloudWatch)

## The Cloud as a Big Data Engine

- Data storage layer
- Data processing layer
- Caching layer
- Language front-ends (e.g., querying)
- Analytics libraries (e.g., ML)
- Continuously streaming data
