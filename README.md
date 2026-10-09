# Unreal Logistics Hybrid Operations Modernization POC

This project is a hands-on Red Hat proof of concept built around a fictional mid-sized company called Unreal Logistics.

The goal was to show how a company could improve the way it manages existing Linux workloads while also creating a gradual path toward containerized applications.

I focused on two areas:

- automating RHEL configuration with Ansible Automation Platform
- containerizing and deploying an application to OpenShift

## The scenario

Unreal Logistics has a small infrastructure team managing Linux virtual machines and applications with a lot of manual work.

The main problems I wanted to address were:

- inconsistent server configuration
- repetitive administration
- manual application deployment
- configuration drift
- growing operational complexity
- no clear path for gradually introducing containers

I intentionally did not design the project around moving every workload to containers.

Some workloads can continue running as VMs while automation makes them easier to manage, while applications that are good candidates for containers can move to OpenShift over time.

## Architecture

```mermaid
flowchart TD
    G[GitHub]

    G --> AAP[Ansible Automation Platform]
    AAP --> RHEL[RHEL 9 VM]

    G --> APP[Operations API]
    APP --> P[Podman]
    P --> Q[Quay.io]

    Q --> OCP[Red Hat OpenShift]
    OCP --> D[Deployment]
    D --> P1[Pod]
    D --> P2[Pod]

    P1 --> S[Service]
    P2 --> S
    S --> R[Route]
    R --> U[User]
    