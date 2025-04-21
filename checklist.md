# ✅ OpenShift 4 Bare Metal Installation Checklist

This checklist is based on the [networknuts/ocp4-metal-install](https://github.com/networknuts/ocp4-metal-install) guide. Follow these steps to perform a successful OpenShift 4 installation on bare metal.

---

## 📋 Prerequisites

- [ ] **Hardware Requirements**: Ensure all nodes meet the minimum hardware specifications.
- [ ] **Network Configuration**: Set up DNS, DHCP, and load balancer as per OpenShift requirements.
- [ ] **RHEL Subscription**: Register all nodes using Red Hat Subscription Manager.

---

## 🔧 Environment Setup

- [ ] Install required packages: `wget`, `git`, `net-tools`, etc.
- [ ] Enable necessary RHEL repositories.
- [ ] Set proper hostnames on each node.
- [ ] Update `/etc/hosts` file with all node entries.

---

## 📦 OpenShift Installation Steps

- [ ] Download the correct version of the OpenShift Installer.
- [ ] Create `install-config.yaml` with cluster details.
- [ ] Generate ignition files using `openshift-install create ignition-configs`.
- [ ] Boot and configure the **bootstrap node** with the ignition file.
- [ ] Provision **master** and **worker** nodes using their respective ignition files.

---

## 🚀 Post-Installation Tasks

- [ ] Approve pending CSRs using `oc get csr` and `oc adm certificate approve <csr-name>`.
- [ ] Verify cluster health with `oc get nodes` and `oc get co`.
- [ ] Set up storage (e.g., via LVM, NFS, or external storage provider).
- [ ] Install necessary OpenShift Operators.
- [ ] Deploy applications and validate workloads.

---

## 📎 Notes

- Refer to the full [installation guide](https://github.com/networknuts/ocp4-metal-install/blob/master/README.md) for exact command-line examples.
- Ensure all nodes have access to the internet or have the necessary RPMs and images cached for disconnected installations.

