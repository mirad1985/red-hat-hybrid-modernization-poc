# Requirements

After looking at Unreal Logistics' current environment, I would keep the first phase of the project focused.

The goal is not to modernize everything at once. The goal is to prove that some of the company's most repetitive infrastructure work can be automated and that there is a practical path toward more consistent application deployment.

## What the business needs

### Reduce repetitive infrastructure work

A lot of the current work depends on administrators manually configuring systems.

For a small infrastructure team, that becomes harder to maintain as the environment grows.

The solution should make common configuration tasks repeatable so administrators do not have to perform the same steps on every server individually.

### Make Linux systems more consistent

Servers that are supposed to serve the same purpose should not gradually become configured differently.

The POC should demonstrate a way to define how a system is supposed to be configured and apply that configuration consistently.

### Modernize without replacing everything

Unreal Logistics still has workloads that make sense as traditional virtual machines.

I would not recommend trying to containerize every application simply because containers are available.

The architecture should allow the company to keep appropriate VM-based workloads while gradually moving suitable applications toward containers.

### Make application deployment more predictable

Application deployment currently depends too heavily on manual steps.

The project should demonstrate a way to package an application consistently and deploy the same artifact into a managed environment.

### Avoid unnecessary complexity

Any new platform introduces operational overhead.

Because Unreal Logistics has a relatively small infrastructure team, the value of a new technology should justify the additional complexity required to operate it.

That is something I would continue evaluating beyond the POC.

## What the POC needs to prove

### RHEL configuration can be automated

The project should use Ansible to configure a Red Hat Enterprise Linux system rather than requiring an administrator to perform each task manually.

### The automation is repeatable

Running the same automation a second time should not keep changing a system that is already configured correctly.

I will test this by running the automation twice and comparing the results.

### Automation can be centrally managed

Rather than only running Ansible from my laptop, the project will use Red Hat Ansible Automation Platform.

This allows the POC to demonstrate inventory management, credential management, execution environments, and centrally launched automation jobs.

### Credentials stay out of source control

SSH keys, API tokens, passwords, and other secrets should never be stored in the public GitHub repository.

Credentials will be managed separately through the platforms that use them.

### An application can be packaged consistently

I will create a small Unreal Logistics application and package it as a container using Podman and a Red Hat Universal Base Image.

The application itself will intentionally be simple because the purpose of the POC is to demonstrate the platform and deployment process rather than application development.

### The container image can be stored centrally

The application image should be stored in a container registry so the deployment platform can retrieve a known version of the application.

### The application can run on OpenShift

The containerized application should deploy successfully to Red Hat OpenShift.

The deployment will run multiple application replicas rather than relying on a single instance.

### OpenShift can maintain desired state

If one of the application Pods is manually removed, OpenShift should recognize that the actual state no longer matches the desired state and automatically create a replacement.

This will demonstrate Kubernetes reconciliation in a way that is easy to see during the final demo.

### Application health can be checked automatically

The application will include a simple health endpoint.

OpenShift will use that endpoint to determine whether the application is ready to receive traffic and whether it is still functioning.

### The application can be reached by a user

The final application should be accessible outside the cluster through an OpenShift Route.

## POC Scope

I am intentionally keeping the implementation small enough that each component can be understood, tested, and explained clearly.

The hands-on portion will include one RHEL 9 virtual machine, Ansible Automation Platform, OpenShift Virtualization, a small containerized application, Podman, a Red Hat Universal Base Image, a container registry, and Red Hat OpenShift.

Other Red Hat technologies may make sense if Unreal Logistics grows.

For example, Satellite could become relevant for managing a much larger RHEL fleet, Advanced Cluster Management could help if the company operates multiple OpenShift clusters, and Advanced Cluster Security could become more important as its container environment expands.

I would treat those as future options rather than adding products to the initial architecture without a clear requirement.
