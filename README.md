# Awesome-Cloud-Instance-Provisioning

## Top Cloud Instance Provisioning Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Bootstrapping, Infrastructure as Code & Configuration Management*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Cloud Instance Provisioning**. These tools enable organizations to automate the creation and configuration of cloud instances—from first-boot initialization and disk manipulation to full infrastructure provisioning and in-VM software management.



**Examples** include Ignition, cloud-init, CoreOS Installer, Terraform, Packer, Ansible, Chef, Puppet, SaltStack, and CloudFormation (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, bootstrapping, and configuration management—ideal for platform engineers, DevOps teams, and organizations seeking transparent, vendor-independent provisioning infrastructure.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[Terraform Cloud (HCP Terraform)](https://www.hashicorp.com/products/terraform)**  

  Managed IaC platform with workspaces, VCS integration, Sentinel/OPA policy as code, private module registry, and config-driven import. **Note**: Resource-based pricing counts every resource in state—teams often find actual count is 3-4x assumed.



- **[AWS CloudFormation](https://aws.amazon.com/cloudformation/)**  

  **AWS-native IaC service** for declaring resources in JSON/YAML templates. Features **stacks, change sets, StackSets** for multi-account/multi-region provisioning, and **IaC Generator** to create templates from existing resources. **The safest choice for AWS-only governance**—tight IAM/Config/CloudTrail integration, automatic state management, and rollbacks .



- **[Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/)**  

  **Azure-native IaC language** providing a cleaner syntax over ARM templates with deep Azure integration.



- **[Pulumi Cloud](https://www.pulumi.com/)**  

  **Cloud-agnostic IaC** using general-purpose programming languages (TypeScript, Python, Go) with managed state and secrets.



- **[Spacelift](https://spacelift.io/)**  

  Multi-IaC orchestration supporting Terraform, OpenTofu, Ansible, Kubernetes, Terragrunt, CloudFormation, and Pulumi. Features policy as code (OPA), stack dependencies, drift detection, and AI assistant with MCP server.



- **[env0](https://www.envzero.com/)**  

  IaC automation platform with flat monthly pricing (not per-resource). Supports Terraform, Terragrunt, and OpenTofu.



## Open-Source GitHub Projects



- **[cloud-init](https://github.com/canonical/cloud-init)**  

  **The de facto multi-distribution package that handles early initialization of a cloud instance** (GPLv3/Apache-2.0) . **The industry standard for cross-platform cloud instance initialization**—supported across all major public cloud providers, private cloud provisioning systems, and bare-metal installations . **During boot, cloud-init identifies the cloud it is running on and initializes the system accordingly**—networking, storage, SSH keys, packages, and various other system aspects are automatically configured during first boot . **The necessary glue between launching a cloud instance and connecting to it** .



- **[Ignition](https://github.com/coreos/ignition)**  

  **A provisioning utility designed specifically for container OSs like Flatcar Container Linux** (Apache-2.0) . **Manipulates disks during early boot**—partitioning disks, formatting partitions, writing files (regular files, systemd units, networkd units), and configuring users . **Runs once in the initramfs**—able to repartition disks, format filesystems, create users, and write files all before userspace begins booting . **Uses JSON instead of YAML**—JSON typing eliminates problems like "off" being rewritten as "false" and versioned configuration allows future development without persistent backward compatibility . **No variable substitution**—use systemd's environment variable expansion to insert dynamic data . **The reference implementation for immutable infrastructure bootstrapping** .



- **[coreos-installer](https://github.com/coreos/coreos-installer)**  

  **A program to assist with installing Fedora CoreOS (FCOS) and Red Hat Enterprise Linux CoreOS (RHCOS)** (Apache-2.0) . **Installs the operating system to a target disk, optionally customizing it with an Ignition config or first-boot kernel parameters** . **Downloads and verifies OS images for cloud, virtualization, or bare metal** . **Embeds Ignition configs in live ISO or PXE initrd images** . **The standard installer for Fedora/RHEL CoreOS** .



- **[Terraform](https://github.com/hashicorp/terraform)**  

  **Industry-standard IaC tool** (MPL-2.0) for provisioning cloud resources via HCL. **The most widely adopted IaC tool** with **62% market share** . **Cloud-agnostic** with hundreds of providers including AWS, Azure, GCP, and SaaS services . **The pragmatic choice for multi-cloud or hybrid strategies**—a single configuration can handle infrastructure across providers . **Trade-off**: State management and collaboration require discipline .



- **[OpenTofu](https://github.com/opentofu/opentofu)**  

  **Open-source Terraform fork under Linux Foundation** (MPL-2.0). Created after HashiCorp's license change to BSL 1.1. Drop-in replacement with community governance. **12% of practitioners currently use it and 27% plan to use it in the future** .



- **[Packer](https://github.com/hashicorp/packer)**  

  **A tool for creating identical machine images for multiple platforms from a single source configuration** (MPL-2.0) . **Packer is lightweight, runs on every major operating system, and is highly performant**—creating machine images for multiple platforms in parallel . **Does not replace configuration management**—Packer is able to use tools like Chef or Puppet to install software onto the image . **A machine image is a single static unit containing a pre-configured OS and installed software** used to quickly create new running machines . **The standard for immutable infrastructure** .



- **[Ansible](https://github.com/ansible/ansible)**  

  **The most widely adopted open-source configuration management and automation platform** (GPL-3.0) . **Agentless architecture via SSH** . **Supports cloud provisioning, configuration management, application deployment, and orchestration** . **The recommended partner to cloud-init**—use cloud-init for minimal system initialization and Ansible for application-level configuration and deployment . **Role-based organization, inventory management, Vault integration, and comprehensive logging** .



- **[Chef](https://github.com/chef/chef)**  

  **Open-source infrastructure automation** (Apache-2.0) . **Configuration management with desired-state enforcement** . **Agent-based architecture** with Chef Infra Client checking in to Chef Infra Server.



- **[Puppet](https://github.com/puppetlabs/puppet)**  

  **Open-source configuration management** (Apache-2.0) . **Desired-state enforcement** with declarative manifests . **The original configuration management tool** for large-scale infrastructure.



- **[SaltStack](https://github.com/saltstack/salt)**  

  **Open-source event-driven automation** (Apache-2.0) . **Remote execution and configuration management** . **Uses Apache Libcloud for cloud provisioning**—Salt Cloud is a cloud provisioning system that makes extensive use of Libcloud to provision and manage cloud VMs .



### Additional Strong Open-Source Options



- **[Terragrunt](https://github.com/gruntwork-io/terragrunt)** — Thin Terraform wrapper (MIT) for DRY configurations and multi-environment orchestration .

- **[Atlantis](https://github.com/runatlantis/atlantis)** — Terraform pull request automation (Apache-2.0) for GitOps workflows.

- **[Pulumi](https://github.com/pulumi/pulumi)** — Open-source IaC SDK (Apache-2.0) using general-purpose programming languages .

- **[Apache Libcloud](https://libcloud.apache.org/)** — Python library for interacting with many cloud providers . **Used by Salt Cloud, mist.io, and others for cloud provisioning** .

- **[Puppet Bolt](https://github.com/puppetlabs/bolt)** — Open-source orchestration tool for on-demand task execution.

- **[Chef InSpec](https://github.com/inspec/inspec)** — Open-source compliance and security testing framework.

- Community **n8n** workflows for provisioning pipeline orchestration and drift alerting.



**Frameworks for building custom systems**: Combine **Terraform** for infrastructure provisioning with **cloud-init** for minimal system initialization, **Ansible** for application configuration, **Packer** for immutable images, and **Ignition** for container OS bootstrapping—creating a fully self-hosted, enterprise-grade provisioning stack .



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Cloud instance provisioning tools handling infrastructure credentials must follow security best practices and comply with applicable regulations.

- **Open-source provisioning is mature and production-ready.** cloud-init is the industry standard for instance initialization . Terraform holds 62% of the IaC market . Ansible is the most widely adopted configuration management tool . **These are genuine alternatives to commercial platforms.**

- **Provisioning vs. configuration management are different problems.** Terraform and CloudFormation provision infrastructure (VMs, networking, databases). Ansible, Chef, Puppet, and SaltStack configure software inside those instances (packages, config files, services) . **The recommended pattern is combining both**: Terraform to provision, Ansible to configure .

- **The cloud-init + Ansible hybrid is the production standard.** Use cloud-init minimally for system initialization (users, SSH keys, network, Docker installation, security) and Ansible for application-level configuration, service deployment, and operational procedures . **This separation improves testability, maintainability, and CI/CD compatibility** .

- **Terraform's license change matters.** HashiCorp moved Terraform to BSL 1.1 in 2023. **OpenTofu is the open-source fork under Linux Foundation governance**—12% of practitioners currently use it and 27% plan to use it .

- Self-hosted open-source solutions require proper state management, secret handling, and ongoing maintenance. **Infrastructure provisioning is security-critical**—state files contain secrets and must be encrypted and access-controlled.



---



**Made for platform engineers, DevOps teams, and organizations building transparent provisioning solutions.**  

Let's make Cloud Instance Provisioning more open, data-driven, and reproducible.
