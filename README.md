# Ansible Network Automation

Learning project focused on network automation with Ansible, starting from a single-device setup and building toward intermediate/professional-grade practices.

## Status: 🟢 Initial Milestone Complete

## What's Working

- ✅ Ansible installed and configured locally
- ✅ Connected to a single Cisco IOS switch over SSH (agentless — no software installed on the device itself)
- ✅ Created a VLAN on the switch using an Ansible playbook (`cisco.ios.ios_vlans`)

## Environment

| Item | Details |
|---|---|
| Automation tool | Ansible (installed on local laptop) |
| Target vendor | Cisco IOS (reference platform) |
| Connection method | SSH (agentless) |
| Key module used | `cisco.ios.ios_vlans` |

> Note: Concepts here transfer directly to other platforms (NX-OS, Arista EOS, Juniper Junos) — only the module names differ.

## Key Principles Learned

- **Agentless architecture** — Ansible pushes config over SSH; nothing runs on the network device.
- **Idempotency** — playbooks should be safe to re-run repeatedly without unintended side effects.
- **Data vs. logic separation** — moving toward driving configs from variables instead of hardcoding values in tasks.

## Repo Structure (so far)

```
.
├── inventory/          # host definitions
├── playbooks/
│   └── vlan.yml        # creates VLAN via ios_vlans
└── README.md
```

*(Update this tree as the repo structure evolves.)*

## Roadmap / Next Steps

- [ ] Identify exact switch vendor/model to tailor trunk, VTP/MST, and check-mode guidance
- [ ] Secure credentials with **Ansible Vault**
- [ ] Scale from one device to many via grouped inventory + group variables
- [ ] Drive configuration from variables rather than hardcoded tasks
- [ ] Interface-level VLAN assignment with `cisco.ios.ios_l2_interfaces`
- [ ] Gather device facts with `cisco.ios.ios_facts` for conditional logic
- [ ] Organize playbooks into **roles** for professional project structure
- [ ] Explore trunk configuration, VTP/MST, and `--check` mode dry runs

## Reference Modules

- `cisco.ios.ios_vlans` — VLAN management
- `cisco.ios.ios_l2_interfaces` — interface-level VLAN/trunk assignment
- `cisco.ios.ios_facts` — device fact gathering

---
