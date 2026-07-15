# Ansible Network Automation

Learning project focused on network automation with Ansible, starting from a single-device setup and building toward intermediate/professional-grade practices.

## Status: 🟢 Expanding from 1 Switch to 3

## What's Working

- ✅ Ansible installed and configured locally
- ✅ Connected to a Cisco IOS switch over SSH (agentless — no software installed on the device itself)
- ✅ Created a VLAN on a switch using an Ansible playbook (`cisco.ios.ios_vlans`)
- ✅ Expanded lab from 1 switch to 3 switches
- ✅ Resolved factory-default management IP conflict — each switch reconfigured with a unique management IP via console cable (RJ45-to-USB, 9600 baud) before joining the shared network
- ✅ Restructured inventory into **grouped format** (`[cisco_switches]` + `[cisco_switches:vars]`) so shared connection variables (username, password, network_os, etc.) live in one place instead of being repeated per host

## Environment

| Item | Details |
|---|---|
| Automation tool | Ansible (installed on local laptop) |
| Target vendor | Cisco IOS (reference platform) |
| Lab size | 3 switches |
| Connection method | SSH (agentless) for Ansible; console cable for initial out-of-band IP assignment |
| Key module used | `cisco.ios.ios_vlans` |
| Inventory format | INI, grouped (`[cisco_switches]`) |

> Note: Concepts here transfer directly to other platforms (NX-OS, Arista EOS, Juniper Junos) — only the module names differ.

## Key Principles Learned

- **Agentless architecture** — Ansible pushes config over SSH; nothing runs on the network device.
- **Idempotency** — playbooks should be safe to re-run repeatedly without unintended side effects.
- **Data vs. logic separation** — moving toward driving configs from variables instead of hardcoding values in tasks.

## Repo Structure (so far)
