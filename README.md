### GitOps with FluxCD for Home Clusters

Kubernetes GitOps using FluxCD for my HomeLAB clusters running on Harvester HCI. This repo targets two clusters: Dev and Prod and aims to keep a common set of manifests between them, using Kustomize to patch values specific for the target clusters.

This is a WIP.

#### How it works

Uses [FluxCD](https://fluxcd.io/docs/) to "synchronise" manifests in this repo to clusters running and managed by me. Each cluster will eventually be consistent with manifests in this repo.

### Configuration

#### Clusters

Two cluster running in Harvester that where provisioned using Rancher Manager.

* Development (dev)
* Production (prod)

#### Infrastructure

For more information about the hardware, you can go to [aaNetworks HomeLAB repo](https://github.com/aaNetworks/HomeLAB)

### Apps

| Workload | Source | Purpose |
| -------- | ------ | ------- |
| [node-red](https://nodered.org/) | raw manifests | Node-RED low code for home automation |
| [adguard]() | helm template | AdGuard Home to block ADs, safe search and browsing |
| [tailscale-operator](https://tailscale.com/kb/1236/kubernetes-operator) helm tempalte | Connecting the cluster to TailNet |


### TODO

General
* Work on this README.md
* Add more apps to the table
* Add more infrastructure details

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

