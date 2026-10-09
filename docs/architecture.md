# Architecture

This POC uses a small environment to show how Unreal Logistics could automate existing RHEL workloads while also beginning to move suitable applications toward containers.

```mermaid
flowchart TD
    G[GitHub Repository]

    G --> AAP[Ansible Automation Platform]
    AAP --> VM[RHEL 9 Virtual Machine]

    G --> APP[Unreal Logistics App]
    APP --> PODMAN[Podman]
    PODMAN --> QUAY[Quay.io]

    QUAY --> OCP[Red Hat OpenShift]
    OCP --> DEPLOY[Deployment - 2 Replicas]
    DEPLOY --> POD1[Application Pod]
    DEPLOY --> POD2[Application Pod]

    POD1 --> SVC[Service]
    POD2 --> SVC
    SVC --> ROUTE[OpenShift Route]
    ROUTE --> USER[User]
    