# Project Setup Guide

This document provides an in-depth rationale for our choices in deploying a fault-tolerant and highly available Ceph distributed storage cluster, integrated with OpenStack, on heterogeneous commodity hardware. These choices have been carefully aligned with the intended learning outcomes (ILOs) of understanding the fundamental concepts of Cloud Computing (CC) and distributed systems, presenting specific concepts in building Cloud solutions, and grasping the fundamentals of CC technology enablers.

## Ubuntu Version: 22.04 LTS (Jammy Jellyfish)

-   **Why**: Ubuntu 22.04 LTS, with its long-term support until April 2027, offers a stable and secure environment essential for a production-grade deployment. Its modern kernel and software compatibility are pivotal in understanding the interplay of operating systems in cloud computing and distributed systems (ILO1). Moreover, its support for advanced features in Ceph and OpenStack facilitates an exploration of computing as a utility and service models like IaaS, crucial in comprehending cloud service orientations (ILO2).
-   **Documentation**: [Ubuntu Release Cycle](https://ubuntu.com/about/release-cycle)

## Ceph Version: Quincy (v17.2.x) specifically: (v17.2.7)

-   **Why**: Quincy v17.2.7 aligns perfectly with Ubuntu 22.04 LTS. This version of Ceph, known for its enhanced performance, security, and usability, is critical for understanding distributed file systems (ILO3). Its selection is strategic for its latest features that support learning about virtualization, containerization, and orchestration - key enablers in cloud computing technology (ILO3). This choice also mirrors the lifecycle of Ubuntu 22.04 LTS, ensuring long-term stability and support.
-   **Supported Ceph Version**: [Supported Ceph Versions](https://ubuntu.com/ceph/docs/supported-ceph-versions)
-   **Documentation**: [Ceph Quincy Release Notes](https://docs.ceph.com/en/latest/releases/quincy/)

## OpenStack Version: Zed

-   **Why**: OpenStack Zed, compatible with Ubuntu 22.04 LTS, represents the cutting edge of cloud storage solutions. Its integration with Ceph underscores the essential principles of service orientation and deployment models in cloud computing (ILO2). The choice of Zed facilitates the understanding of the latest developments in cloud infrastructure, essential for grasping the evolving economic and social trends in cloud computing (ILO2).
-   **Documentation**: [OpenStack Releases](https://www.openstack.org/software/)
-   **OpenStack Packages for Ubuntu**: [OpenStack Packages](https://docs.openstack.org/install-guide/environment-packages-ubuntu.html)

## Key Documentation Resources and Publications

To ensure the successful deployment and management of our Ceph distributed storage cluster and OpenStack integration, we will rely on the following key documentation resources and publications:

-   **Ubuntu Documentation**:Critical for grasping system requirements and maintenance practices, which are fundamental in understanding the role of operating systems in cloud computing and distributed systems (ILO1). [Ubuntu Documentation](https://help.ubuntu.com/)
-   **Ceph Documentation**: Indispensable for deployment strategies and performance tuning, providing insights into distributed file systems and storage solutions in cloud computing (ILO3). [Ceph Official Documentation](https://docs.ceph.com/en/latest/)
-   **OpenStack Documentation**: Offers comprehensive guides on deploying and managing OpenStack, crucial for understanding cloud service models and deployment strategies (ILO2). [OpenStack Documentation](https://docs.openstack.org/)

## Conclusion

The selection of Ubuntu 22.04 LTS (Jammy Jellyfish), Ceph Quincy (v17.2.7), and OpenStack Zed provides a solid foundation for deploying a Ceph distributed storage cluster, fully integrated with OpenStack. This setup is not only aimed at achieving high availability and fault tolerance but also at comprehensively meeting the learning objectives related to cloud computing and distributed systems. The chosen versions ensure compatibility, stability, and access to the latest features, fostering an in-depth understanding of the technological, economic, and social dimensions of cloud computing. The selected key documentation resources and publications will guide our deployment, ensuring best practices are followed and the infrastructure is optimized for performance and reliability.