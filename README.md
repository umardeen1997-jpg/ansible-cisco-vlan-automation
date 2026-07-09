# Cisco Small Business VLAN Automation using Ansible

## Overview

Automated VLAN creation on a physical Cisco Small Business switch using Ansible over SSH.

## Environment

- Ubuntu Linux
- Ansible 2.16
- Cisco Small Business Switch
- SSH

## What this project does

- Connects to Cisco switch using Ansible
- Handles legacy SSH compatibility
- Automates VLAN creation
- Verifies VLAN configuration

## Problem Solved

Cisco Small Business switches require interactive CLI configuration.
Standard Ansible IOS VLAN modules were not compatible.

Solution:
Used ansible.netcommon.cli_command with interactive prompt handling.

## VLANs Created

| VLAN ID | Name |
|---|---|
|10|SALES|
|60|TEST-ANSIBLE|
|70|Testing|

## Verification

Command:

show vlan

Output:

VLANs successfully created.
