### GitOps with FluxCD for Home Clusters

Kubernetes GitOps using FluxCD for my HomeLAB clusters running on [Talos](https://www.talos.dev/), [Omni](https://omni.siderolabs.com/) and [Incus](https://linuxcontainers.org/incus/). This repo targets two clusters: Dev and Prod and aims to keep a common set of manifests between them, using Kustomize to patch values specific for the target cluster.

This is a WIP.

#### How it works

Uses [FluxCD](https://fluxcd.io/docs/) to "synchronise" manifests in this repo to clusters running and managed by me. Each cluster will eventually be consistent with manifests in this repo.

### Configuration

#### Clusters

Two cluster running Talos on Incus provisioned using Omni.

* Development - [dev](clusters/dev/)
* Production - [prod](clusters/prod/)

#### Infrastructure

For more information about the hardware, you can go to [aaNetworks HomeLAB repo](https://github.com/aaNetworks/HomeLAB)

### Apps

| Workload | Source | Purpose |
| -------- | ------ | ------- |
| [node-red](https://nodered.org/) | raw manifests | Node-RED low code for home automation |
| [adguard](https://github.com/AdguardTeam/AdGuardHome) | helm template | AdGuard Home to block ADs, safe search and browsing |
| [cert-manager](https://cert-manager.io/) | helm template | Certificate management for ingress |
| [tailscale-operator](https://tailscale.com/kb/1236/kubernetes-operator) | helm tempalte | Connecting the cluster to TailNet |
| [harbor](https://goharbor.io/) | helm template | container repository for Kubernetes |

### TODO

General

- [x] Work on this README.md
- [x] Add more apps to the table
- [ ] Add more infrastructure details
- [ ] Add FluxCD directly from Omni cluster-template.

Backup

 - [ ] Backup data
 - [ ] Deploy grafana operator

Secrets

 - [x] Deploy external-secrets-operator
 - [x] Provisioning of secrets to vault
 - [ ] Migrate zigbeemqtt mqtt creds to vault
 - [ ] Migrate zigbeemqtt keys to vault

Maintain

 - [ ] Renovate
