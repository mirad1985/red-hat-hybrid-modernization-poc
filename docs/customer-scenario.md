# Unreal Logistics Customer Scenario

## Company Overview

Unreal Logistics is a fictional mid-sized logistics company with approximately 500 employees.

The company relies on internal applications to support logistics operations, inventory coordination, administrative processes, and other day-to-day business functions.

As the organization has grown, its IT environment has become increasingly difficult for a small infrastructure team to manage consistently.

## Current Environment

Unreal Logistics currently operates:

- Linux-based virtual machines
- manually configured Linux servers
- administrator-driven application deployments
- a growing hybrid IT environment
- several applications that still depend on traditional virtual machines
- a small infrastructure and operations team

The company does not currently have a standardized automation strategy or container application platform.

## Current Challenges

### 1. Manual server configuration

Administrators configure many systems manually.

This creates several problems:

- repetitive work
- inconsistent configurations
- higher risk of human error
- difficulty reproducing configurations across environments

As the number of systems grows, this approach becomes increasingly difficult to maintain.

### 2. Configuration drift

Servers that were originally configured similarly can gradually become different.

For example:

- one server receives an update while another does not
- configuration files are changed manually
- packages differ between systems
- services are enabled differently

This makes troubleshooting and maintenance more difficult.

### 3. Manual application deployment

Application deployments rely heavily on administrators performing individual steps.

This can make deployments:

- slower
- harder to reproduce
- dependent on individual knowledge
- more susceptible to mistakes

### 4. Increasing operational complexity

Unreal Logistics is expanding its infrastructure while operating with a relatively small IT team.

If operational processes remain primarily manual, the amount of administrative work will continue increasing as the environment grows.

### 5. No standardized modernization path

Some existing workloads still make sense as virtual machines, while other applications could benefit from containerization.

Unreal Logistics does not want to replace every workload immediately.

Instead, the company needs a strategy that allows traditional virtual machines and modern containerized applications to coexist during a gradual modernization effort.

## Business Objectives

Unreal Logistics wants to:

1. reduce repetitive infrastructure administration
2. improve consistency across Linux systems
3. create repeatable automation processes
4. improve application deployment consistency
5. introduce containerized application delivery
6. maintain existing virtual machine workloads where appropriate
7. create a gradual rather than disruptive modernization strategy
8. keep operational complexity manageable for a small IT team

## Modernization Approach

Rather than replacing the existing environment immediately, the proposed approach uses a phased modernization strategy.

The proof of concept will explore how Red Hat technologies can support:

- standardized enterprise Linux infrastructure with Red Hat Enterprise Linux
- repeatable infrastructure automation with Red Hat Ansible Automation Platform
- continued support for VM-based workloads through OpenShift Virtualization
- containerized application delivery with Podman and Red Hat Universal Base Images
- centralized container image storage
- deployment and management of containerized applications with Red Hat OpenShift

The goal of the proof of concept is not to demonstrate that every Unreal Logistics workload should use every Red Hat product.

Instead, the goal is to determine how these technologies could address specific customer requirements and where they would provide meaningful operational value.