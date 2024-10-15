<div align="center">

# 🪨 Homelab 🏡

Repository for home infrastructure and [Kubernetes](https://kubernetes.io/) cluster
using [GitOps](https://en.wikipedia.org/wiki/DevOps) practices.

Held together using [Proxmox VE](https://www.proxmox.com/en/proxmox-virtual-environment),
[Terraform](https://www.terraform.io/), [Talos](https://talos.dev), [Kubernetes](https://kubernetes.io/),
[Argo CD](https://argoproj.github.io/cd/) and copious amounts of [YAML](https://yaml.org/)

</div>

---

## 📖 Overview

This repository hosts the IaC ([Infrastructure as Code](https://en.wikipedia.org/wiki/Infrastructure_as_code))
configuration for my homelab kubernetes cluster. This project was inspired (and forked from) a project by [vehagn](https://github.com/vehagn).
I have elected to remove some of his deployments as they are not relevant for my use case, but I am thankful for all the work he put into this project!

The Homelab is backed by [Proxmox VE](https://www.proxmox.com/en/proxmox-virtual-environment) hypervisor nodes with VMs
bootstrapped using [Terraform](https://www.terraform.io/).

Most of the services run on [Talos](https://www.talos.dev/) flavoured [Kubernetes](https://kubernetes.io/).

## 🧑‍💻 Getting Started

Todo - Explain how to use this repo given my use case.

## ⚙️ Core Components

* [Proxmox VE](https://www.proxmox.com/en/proxmox-virtual-environment): Server management and KVM hypervisor.
* [Terraform](https://www.terraform.io/): Infrastructure as code tool.
* [Cilium](https://cilium.io/): eBPF-based Networking, Observability, Security.
* [Proxmox CSI Plugin](https://github.com/sergelogvinov/proxmox-csi-plugin): CSI driver for storage
* [Argo CD](https://argo-cd.readthedocs.io/en/stable/): Declarative, GitOps continuous delivery tool for Kubernetes.
* [Cert-manager](https://cert-manager.io/): Cloud native certificate management.
* [Sealed-secrets](https://github.com/bitnami-labs/sealed-secrets): Encrypt your Secret into a SealedSecret, which is
  safe to store - even inside a public repository.
* [Keycloak](https://www.keycloak.org/): Open source identity and access management
* [Gateway API](https://gateway-api.sigs.k8s.io/): Next generation of Kubernetes Ingress
* [AdGuardHome](https://github.com/AdguardTeam/AdGuardHome): Domain name server backed by Unbound
* [Netbird](https://netbird.io/): Completely self hosted VPN solution

## 🗃️ Folder Structure

```shell
.
├── 📂 docs                # Documentation
├── 📂 k8s                 # Kubernetes manifests
│   ├── 📂 apps            # Applications
│   ├── 📂 infra           # Infrastructure components
│   └── 📂 sets            # Bootstrapping ApplicationSets
└── 📂 tofu                # Tofu configuration
    └── 📂 kubernetes      # Kubernetes VM configuration
        ├── 📂 bootstrap   # Kubernetes bootstrap config
        └── 📂 talos       # Talos configuration 
```

## 🖥️ Hardware

| Name | Device                     | CPU                 | RAM         | Storage                            | Purpose          |
|------|----------------------------|---------------------|-------------|------------------------------------|------------------|
| neko | Dell R730 Rackmount Server | 2 x Xeon E5-2696 v3 | 128 GB DDR4 | 560GB Boot Disk                    | VM Host, Storage |
|      |                            |                     |             | 3 x 4TB RaidZ1 pool (pve-zfs) 11TB |                  |
|      |                            |                     |             | 4 x 10TB RaidZ1 pool (tank) 36.5TB |                  |

## 🏗️ Work in Progress

- [ ] Everything (I need to make the repo work for my infra)

## 👷‍ Future Projects

- [ ] OPNSense/pfSense/OpenWRT
- [ ] Implement LGTM-stack for monitoring
- [ ] Use BGP instead of ARP in Cilium
- [ ] Cilium mTLS & SPIFFE/SPIRE
- [ ] Ceph for distributed storage
- [ ] Dynamic Resource Allocation for GPU
