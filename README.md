# Project Setup Guide

This document outlines our choices for the Linux Ubuntu version, Ceph version, and OpenStack version for deploying a fault-tolerant and highly available Ceph distributed storage cluster integrated with OpenStack. Our decisions are based on ensuring compatibility, stability, and performance across all components of our deployment.

## Ubuntu Version: 22.04 LTS (Jammy Jellyfish)

-   **Why**: Ubuntu 22.04 LTS is chosen for its long-term support until April 2027, providing the stability and security necessary for production environments. Its modern kernel and software stack are crucial for supporting the latest features of Ceph and OpenStack, enhancing hardware compatibility and overall system performance.
-   **Documentation**: [Ubuntu Release Cycle](https://ubuntu.com/about/release-cycle)

## Ceph Version: Quincy (v17.2.x) specifically: (v17.2.7)

-   **Why**: Among Ceph's releases, Quincy v17.2.7 stands out for its compatibility with Ubuntu 22.04 LTS, offering enhanced performance, security, and usability. We selected Quincy for its latest features and improvements, aligning with our goal for long-term support and stability, mirroring the lifecycle of Ubuntu 22.04 LTS.
-   **Supported Ceph Version**: [Supported Ceph Versions](https://ubuntu.com/ceph/docs/supported-ceph-versions)
-   **Documentation**: [Ceph Quincy Release Notes](https://docs.ceph.com/en/latest/releases/quincy/)

## OpenStack Version: Zed

-   **Why**: OpenStack Zed, being the latest release at the time of our deployment, is chosen for its compatibility with Ubuntu 22.04 LTS. It supports the most recent dependencies and introduces new features that significantly enhance cloud storage solutions when integrated with Ceph. Zed offers the most advanced features and improvements, ensuring our cloud infrastructure is at the forefront of technology.
-   **Documentation**: [OpenStack Releases](https://www.openstack.org/software/)
-   **OpenStack Packages for Ubuntu**: [OpenStack Packages](https://docs.openstack.org/install-guide/environment-packages-ubuntu.html)

## Key Documentation Resources and Publications

To ensure the successful deployment and management of our Ceph distributed storage cluster and OpenStack integration, we will rely on the following key documentation resources and publications:

-   **Ubuntu Documentation**: For understanding system requirements, installation procedures, and maintenance practices. [Ubuntu Documentation](https://help.ubuntu.com/)
-   **Ceph Documentation**: Essential for deployment strategies, configuration options, and performance tuning of our Ceph cluster. [Ceph Official Documentation](https://docs.ceph.com/en/latest/)
-   **OpenStack Documentation**: Provides comprehensive guides on deploying and managing OpenStack, including integration with Ceph for cloud storage solutions. [OpenStack Documentation](https://docs.openstack.org/)

## Conclusion

The combination of Ubuntu 22.04 LTS (Jammy Jellyfish), Ceph Quincy (v17.2.7), and OpenStack Zed provides a robust foundation for deploying a highly available and fault-tolerant Ceph distributed storage cluster, fully integrated with OpenStack. By adhering to the latest versions of these platforms, we ensure compatibility, stability, and access to the most recent features and improvements. The selected key documentation resources and publications will guide our deployment, ensuring best practices are followed and the infrastructure is optimized for performance and reliability.
