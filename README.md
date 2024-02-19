# Project 1 (Milstone 1 + Milestone 2)

This document provides an in-depth rationale for our choices in deploying a fault-tolerant and highly available Ceph distributed storage cluster, integrated with OpenStack, on heterogeneous commodity hardware. These choices have been carefully aligned with the intended learning outcomes (ILOs) of understanding the fundamental concepts of Cloud Computing (CC) and distributed systems, presenting specific concepts in building Cloud solutions, and grasping the fundamentals of CC technology enablers.
Ceph is a highly scalable and high-performance distributed file system, designed to manage vast amounts of data across a range of applications and infrastructures.

Supported Ceph versions are associated with supported stable Ubuntu LTS releases:

18.2.x (Reef) on Ubuntu 22.04 LTS (Jammy)
17.2.x (Quincy) on Ubuntu 22.04 LTS (Jammy)


## Concept and Architecture

Ceph diverges from traditional storage systems by combining processors and memory with disk drives. 
This design delegates low-level allocation to Object Storage Devices (OSDs) and separates I/O operations (read/write) from metadata operations (file open/close).
It is designed to scale to hundreds of petabytes, addressing limitations of earlier systems by eliminating traditional file allocation tables.
Ceph's architecture includes clients, a cluster of OSDs for storing all data and metadata, and a metadata server cluster managing the file system namespace.

## Unique Features

Decoupled Data and Metadata: By replacing allocation tables with a pseudo-random data distribution function (CRUSH), Ceph maximizes separation between data and metadata management.
CRUSH Algorithm: Facilitates dynamic and reliable distribution of data across a heterogeneous cluster, ensuring data safety and optimizing resource utilization.
OSD Intelligence: OSDs in Ceph are semi-autonomous, distributing data replication, failure detection, and recovery tasks, thus improving system reliability and scalability.

## Performance

Metadata Management: Ceph's dynamic distributed metadata cluster architecture dramatically enhances the scalability of metadata access and overall system performance.
Client Operation: Clients interact directly with OSDs for file I/O, while metadata operations are handled by the metadata server cluster. This design improves system efficiency and response time.
Ceph separates data synchronization (visibility to clients) from data safety (replication and durability), providing a balance between performance and reliability.

## Integration and Use Cases

Ceph is suitable for a range of general-purpose and scientific computing file system workloads.
Future Extensions: Planned improvements include enhanced security protocols, POSIX IO extensions for high-performance computing, and quality of service features for storage management.

## Challenges and Solutions

Scalability and Efficiency: The design of Ceph addresses the challenges of scalability and efficient metadata management in distributed file systems, surpassing existing systems in terms of performance.
Data Distribution: The use of CRUSH and intelligent OSDs allows Ceph to effectively manage data distribution and replication, crucial for large-scale systems.

## Matrix Referenced

The following Matrix provides a detailed rationale for the selection of Ubuntu 22.04 LTS (Jammy Jellyfish), Ceph Quincy (v17.2.x), and OpenStack Zed for the deployment of a Ceph distributed storage cluster, integrated with OpenStack, on heterogeneous commodity hardware. We will go in depth to explain the rationale for each choice, the evidence considered, and the documentation resources used to validate these choices.

![image](https://github.com/AyoubMaimmadi/SP24-CSC537401-Project_1/assets/46249118/ee7d227c-67d5-4f8e-a6c1-fdfbcdb4f94d)

## Ubuntu Version: 22.04 LTS (Jammy Jellyfish)

-   **Evidences to consider**:

Compatibility: Checking Ubuntu’s release notes and Ceph/OpenStack documentation for compatibility with specific Ubuntu versions.
Long-Term Support (LTS) Releases: LTS versions offer extended support, making them a preferred choice for stability and long-term maintenance.
Security and Stability Updates: Reviewing the release and patch history for insights into the stability and security of the Ubuntu versions.

-   **Why**: Ubuntu 22.04 LTS, with its long-term support until April 2027, offers a stable and secure environment essential for a production-grade deployment. Its modern kernel and software compatibility are pivotal in understanding the interplay of operating systems in cloud computing and distributed systems (ILO1). Moreover, its support for advanced features in Ceph and OpenStack facilitates an exploration of computing as a utility and service models like IaaS, crucial in comprehending cloud service orientations (ILO2).
-   **Documentation**: [Ubuntu Release Cycle](https://ubuntu.com/about/release-cycle)

## Ceph Version: Quincy (v17.2.x)

-   **Evidence to Consider:**

Release Compatibility: Ensuring that the chosen Ceph version is compatible with the selected Ubuntu version.
Feature Set and Improvements: Analyzing the features of different Ceph versions and how they align with project requirements.
Performance Metrics: Looking for performance benchmarks comparing different Ceph versions.

-   **Why**: Quincy v17.2.x aligns perfectly with Ubuntu 22.04 LTS. This version of Ceph, known for its enhanced performance, security, and usability, is critical for understanding distributed file systems (ILO3). Its selection is strategic for its latest features that support learning about virtualization, containerization, and orchestration - key enablers in cloud computing technology (ILO3). This choice also mirrors the lifecycle of Ubuntu 22.04 LTS, ensuring long-term stability and support.
-   **Supported Ceph Version**: [Supported Ceph Versions](https://ubuntu.com/ceph/docs/supported-ceph-versions)
-   **Documentation**: [Ceph Quincy Release Notes](https://docs.ceph.com/en/latest/releases/quincy/)

## OpenStack Version: Zed

-   **Evidence to Consider:**

We previously confirmed the compatibility of both Ceph Quincy and OpenStack Zed with Ubuntu 22.04 LTS. However, upon further review, we realized the critical importance of directly verifying the compatibility between Ceph Quincy and OpenStack Zed to ensure seamless integration and functionality of our cloud infrastructure. This oversight was highlighted by our professor, underscoring the potential risks of integration issues that could necessitate a reassessment of our chosen versions.

Documentation and tutorials suggest that OpenStack Zed and Ceph Quincy are intended to work together, as part of a cloud computing infrastructure leveraging Ceph's storage solutions within an OpenStack environment​​​​​​. Specifically, guides for deploying a Charmed OpenStack cloud include setups using Ubuntu 22.04 LTS, OpenStack Zed, and Ceph Quincy, indicating a level of prepared integration and compatibility​​. [Evidence of Compatibility](https://docs.openstack.org/charm-guide/zed/getting-started/index.html)

## Note

When we reviewed the Ceph Quincy Release Notes and [Ubuntu's Ceph Documentation](https://ubuntu.com/ceph/docs/supported-ceph-versions) we confirmed that Ceph Quincy v17.2.x is compatible with Ubuntu 22.04 LTS as well. Ensuring compatibility between Ceph, OpenStack, and the operating system is crucial for a stable and efficient cloud environment. Thoroughly reviewing official documentation, engaging with community forums, and conducting tests in controlled environments are effective strategies for validating the compatibility of these versions.

-   **Documentation**: [OpenStack Releases](https://www.openstack.org/software/)
-   **OpenStack Packages for Ubuntu**: [OpenStack Packages](https://docs.openstack.org/install-guide/environment-packages-ubuntu.html)

## Key Documentation Resources and Publications

To ensure the successful deployment and management of our Ceph distributed storage cluster and OpenStack integration, we will rely on the following key documentation resources and publications:

-   **Ubuntu Documentation**:Critical for grasping system requirements and maintenance practices, which are fundamental in understanding the role of operating systems in cloud computing and distributed systems (ILO1). [Ubuntu Documentation](https://help.ubuntu.com/)
-   **Ceph Documentation**: Indispensable for deployment strategies and performance tuning, providing insights into distributed file systems and storage solutions in cloud computing (ILO3). [Ceph Official Documentation](https://docs.ceph.com/en/latest/)
-   **OpenStack Documentation**: Offers comprehensive guides on deploying and managing OpenStack, crucial for understanding cloud service models and deployment strategies (ILO2). [OpenStack Documentation](https://docs.openstack.org/)

## Conclusion

The selection of Ubuntu 22.04 LTS (Jammy Jellyfish), Ceph Quincy (v17.2.x), and OpenStack Zed provides a solid foundation for deploying a Ceph distributed storage cluster, fully integrated with OpenStack. This setup is not only aimed at achieving high availability and fault tolerance but also at comprehensively meeting the learning objectives related to cloud computing and distributed systems. The chosen versions ensure compatibility, stability, and access to the latest features, fostering an in-depth understanding of the technological, economic, and social dimensions of cloud computing. The selected key documentation resources and publications will guide our deployment, ensuring best practices are followed and the infrastructure is optimized for performance and reliability.

# Milestone 2 Report: Ceph Storage Cluster Deployment

## Ubuntu Installation Confirmation

As part of the initial phase of our project, we have successfully installed Ubuntu 22.04 LTS (Jammy Jellyfish) on all three heterogeneous commodity machines allocated to our team in the Linux lab. This installation establishes a stable and secure foundation for deploying our Ceph distributed storage cluster, aligned with our project's requirements for a fault-tolerant and highly available system.

### Installation Details

-   **Ubuntu Version:** 22.04 LTS (Jammy Jellyfish)
-   **Installation Date:** 2/14/2024

## Suggested Ceph Storage Cluster Architecture if we had the opportunity to work with at least 7 nodes:

Given the scope of our project and the need for simplicity in implementation, we propose the following simplified Ceph storage cluster architecture. This setup ensures a basic level of fault tolerance and high availability while being straightforward to deploy.

### Cluster Size and Composition:

- Minimum of three nodes to ensure high availability and fault tolerance. In our case, we only have three nodes. (Check Final Proposed Architecture below)
- Each node should have sufficient CPU, RAM, and storage capacity to handle the demands of the Ceph cluster.

### Ceph Monitors (MONs):

- Deploy at least three MONs for quorum and redundancy, distributed across different nodes. In our case, we only have three nodes. (Check Final Proposed Architecture below)
- MONs are responsible for maintaining the master copy of the cluster map and ensuring coherency in the cluster.

### Ceph Managers (MGRs):

- Deploy at least two MGRs for high availability, ideally on separate nodes from MONs.In our case, we only have three nodes. (Check Final Proposed Architecture below)
- MGRs provide additional monitoring and management capabilities to the cluster.

### Ceph Object Storage Daemons (OSDs):

- Deploy multiple OSDs, ideally at least one per node. In our case, we only have three nodes. (Check Final Proposed Architecture below)
- OSDs are responsible for storing data, handling data replication, recovery, and rebalancing.

### Ceph Metadata Servers (MDSs):

- Deploy at least two MDSs if CephFS (Ceph Filesystem) is used. In our case, we only have three nodes. (Check Final Proposed Architecture below)
- MDSs manage the file system namespace and metadata for CephFS.

### Network Design:

- Separate networks for public (client access) and cluster (internal communication) traffic.
- Ensure high-bandwidth and low-latency networking.

### Ceph Components/Daemons to Install

#### On MON Nodes:

- Install Ceph-MON to manage the cluster state and consensus.
- Optionally, co-locate Ceph-MGR on MON nodes for management and monitoring.

#### On OSD Nodes:

- Install Ceph-OSD on each node managing a storage device.
- Ensure each OSD node has a dedicated storage device (HDD/SSD) for Ceph.

#### On MDS Nodes (if using CephFS):

- Install Ceph-MDS on dedicated nodes or co-located with other daemons but ensure resource availability.


### Final Proposed 3-Nodes Architecture

-   **1 Ceph Monitor (MON):** Deployed on Machine 1. Although a production environment recommends at least three MONs for quorum and redundancy, our simplified project scope allows for a single MON to suffice for learning purposes.
-   **3 Ceph Object Storage Daemons (OSDs):** One OSD deployed on each machine. This setup ensures data is distributed across the cluster, leveraging Ceph's inherent data replication and fault tolerance capabilities.
-   **1 Ceph Manager (MGR):** Co-located with the Ceph Monitor on Machine 1. The MGR provides essential cluster management and monitoring functionalities.

### Ceph Components Explanation

#### Ceph-MON (Monitor)

-   **What it does:** Ceph Monitor (MON) maintains a master copy of the cluster map, a critical component of the Ceph network that keeps track of all the metadata about the cluster state, including the OSD map (which OSDs are up and down), the PG map (placement group mappings), and the CRUSH map (a hierarchical layout of the cluster). The MON ensures that the cluster remains coherent by maintaining quorum among the cluster's nodes, making it essential for cluster management and state consensus.

#### Ceph-MGR (Manager)

-   **What it does:** Ceph Manager (MGR) provides additional monitoring and management capabilities to the Ceph cluster. It collects runtime metrics, provides dashboard interfaces for visualizing cluster status, and supports a range of management commands. The MGR is crucial for efficient cluster operation and performance monitoring, making cluster administration tasks easier and more straightforward.

#### Ceph-OSD (Object Storage Daemon)

-   **What it does:** Ceph Object Storage Daemons (OSDs) are responsible for storing data, handling data replication, recovery, rebalancing, and providing some monitoring information to Ceph Monitors and Managers. Each OSD manages a local storage device (e.g., a hard disk or SSD) and participates in the Ceph cluster's network, serving client requests to read and write data. The OSDs are the backbone of the Ceph storage system, ensuring data redundancy, fault tolerance, and high availability.

### Components/Daemons to Install

-   **On Machine 1:** Ceph-MON, Ceph-MGR
-   **On Machines 1, 2 and 3:** Ceph-OSD

This architecture provides a balance between simplicity and the demonstration of Ceph's capabilities. It allows for the exploration of Ceph's distributed storage functionalities with minimal complexity, suitable for an educational project.

### Conclusion

This simplified architecture allows our team to focus on understanding and demonstrating the core functionalities of Ceph in a controlled environment. By reducing the complexity of the deployment, we can more effectively manage our learning objectives and project deliverables within the given timeframe.
