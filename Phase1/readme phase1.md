# Phase 1: Setup and Attack
## Setup
- Kali Linux: `10.0.2.4`, Metasploitable3: `10.0.2.15`.
- Both VMs on `ICS344Net`, connectivity confirmed (see Setup folder).
## Service Selection
- Selected SSH due to weak credentials (see Service_Selection.md).
## Attacks
- Metasploit: Used `ssh_login` to gain `vagrant` access (see Attacks/Metasploit).
- Custom Script: Python script using `paramiko` to connect via SSH (see Attacks/CustomScript).
