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

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global Infrastructure as Code (IaC) and cloud instance provisioning market is estimated at **$1.3B–$1.6B in 2025–2026** (scaling past **$6B+ by the early 2030s** at a ~20–25% CAGR), or upwards of **$39B+** when encompassing adjacent cloud automation and provisioning frameworks. The sector remains **moderately fragmented**—while hyperscaler-native tools dominate single-cloud footprints, multi-cloud enterprise mandates and ecosystem shifts (such as HashiCorp's BSL licensing change and the emergence of OpenTofu) have spurred healthy competition across independent orchestration, drift detection, and multi-IaC platforms rather than a single winner-take-all monopoly.

## SaaS/Hosted Platforms

| Platform | Company Valuation / Revenue (Size) | Starting Price (Paid) | Free Tier / Trial Limits | Description |
| :--- | :--- | :--- | :--- | :--- |
| **[Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/)** (Microsoft) | **~$3.8T–$4.0T Market Cap** ($318.3B TTM Revenue) | **$0** (Free core tooling; underlying Azure compute/storage billed at standard pay-as-you-go rates) | **Forever Free** (100% free & open-source CLI, compiler, and language with no usage caps; underlying resources eligible for Azure Free Account: $200 credit for 30 days + 55+ always-free services) | Azure-native IaC language offering clean syntax, modular templates, and first-class integration with Azure Resource Manager (ARM). |
| **[AWS CloudFormation](https://aws.amazon.com/cloudformation/)** (Amazon AWS) | **~$2.7T–$2.8T Market Cap** ($638B–$742B TTM Revenue) | **$0** (Free for native `AWS::*` templates; custom extensions charge $0.0009 per handler operation beyond free tier) | **Forever Free** for all native `AWS::*` resource provisioning; Registry extensions include **1,000 handler operations/month** free per account; underlying AWS resources apply to standard AWS 12-month / always-free tier limits | AWS-native declarative IaC service featuring stacks, Change Sets, StackSets for multi-region/multi-account rollout, and IaC Generator. |
| **[Terraform Cloud (HCP Terraform)](https://www.hashicorp.com/products/terraform)** (HashiCorp / IBM) | **$6.4B Valuation** (Acquired by IBM; $583M annual revenue) | **$0.10 / resource / month** (Essentials tier; Standard starts at $0.47 / resource / month) | **Forever Free up to 500 managed resources**, unlimited users, 1 concurrent run, private module registry, and VCS-driven workflows | Managed IaC platform offering remote execution, private module registry, drift detection, and OPA/Sentinel policy as code. |
| **[Pulumi Cloud](https://www.pulumi.com/)** (Pulumi) | **~$100M–$400M Valuation** ($99M funding; ~$17M–$20M ARR) | **$40 / month** (Essentials tier with 40 credits; Pro starts at $400 / month with 400 credits) | **Forever Free for 1 user** with **unlimited resources**, unlimited projects/stacks, and 500 Deployments minutes/month | General-purpose programming language IaC (TypeScript, Python, Go) with managed state, secrets management (ESC), and CI/CD automation. |
| **[Spacelift](https://spacelift.io/)** (Spacelift) | **~$73.6M Total Funding** (~$15M–$20M ARR) | **$20,000 / year** (~$1,667 / month for Starter+ tier with 1 private worker and unlimited users) | **Forever Free for up to 2 users**, 1 concurrent run (public worker), unlimited stacks, and full IaC support (Terraform, OpenTofu, Pulumi, CloudFormation, Ansible); also offers a **14-day free trial** of paid tiers (no credit card required) | Sophisticated multi-IaC orchestration platform featuring OPA policy-as-code, stack dependencies, drift detection, and AI assistant. |
| **[env0](https://www.envzero.com/)** (env0) | **~$42M Total Funding** (~$6M–$9M ARR) | **~$1,500 / month** ($18,000 / year base for Cloud Navigator on AWS Marketplace; custom quotes per active env / apply) | **Forever Free up to 250 runs/month**, up to **30 active environments**, unlimited users, 1 concurrent deployment, and 1 self-hosted agent | Collaborative IaC automation and management platform supporting Terraform, Terragrunt, OpenTofu, and Pulumi with built-in cloud cost tracking. |



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
