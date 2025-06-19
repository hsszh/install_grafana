# Grafana Installation with Ansible

## Overview

This Ansible playbook automates the installation and configuration of **Grafana Enterprise** on target Linux systems. It supports both **Debian-based** and **Red Hat-based** distributions.

The playbook performs the following actions:

---

## What It Does

### ✅ Platform Detection
- Detects the target system's operating system family using `ansible_os_family` and installs Grafana accordingly.

---

### 🐧 Debian-Based Systems (e.g. Ubuntu, Debian)
1. Downloads the official **Grafana GPG key**.
2. Adds the **Grafana APT repository** using `apt_repository`.
3. Installs the `grafana-enterprise` package using `apt`.

---

### 🔴 Red Hat-Based Systems (e.g. RHEL, CentOS, Rocky)
1. Downloads the official **Grafana GPG key**.
2. Adds the **Grafana YUM/DNF repository**.
3. Installs the `grafana-enterprise` package using `dnf`.

---

### 🔥 Firewalld Configuration
1. Checks if `firewalld` is running on the target system.
2. If it is, opens **port 3000/tcp** permanently to allow access to Grafana's web interface.

---

### 📡 Service Management
- Starts and enables the **Grafana server service** (`grafana-server`) to ensure it runs on boot.


