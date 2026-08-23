# sec-lab

A SOC lab I built on my home Proxmox cluster. Wazuh SIEM watching monitored endpoints, Sigma rules I wrote and tagged to MITRE ATT&CK, and IR playbooks I'd want a junior analyst to actually be able to follow.

Not a tutorial repo. Not a study guide. The actual tooling I run, plus the rules and playbooks I keep refining as I work through detections.

## What's here

- [siem/](siem/): Wazuh deployment, custom rules, agent enrollment, Sigma-to-Wazuh conversion
- [detection/](detection/): Sigma rules named per MITRE technique, with tactic and technique tags
- [playbooks/](playbooks/): IR runbooks for common scenarios
- [hardening/](hardening/): OS and service baselines I actually apply
- [monitoring/](monitoring/): telemetry and dashboard configs
- [automation/](automation/): triage and response scripts in Python and Shell
- [plans/](plans/): roadmap and phase planning

## Lab stack

| Component | Details |
|---|---|
| SIEM | Wazuh 4.14.4 all-in-one (manager + indexer + dashboard) |
| Endpoints | Debian 12 LXC containers on a 3-node Proxmox VE 9.1.6 HA cluster |
| Detection | Built-in rules plus custom rules with MITRE ATT&CK mapping |
| Alerting | Email via msmtp/Gmail for high-severity events |
| Monitoring | Grafana + Prometheus for infra, Wazuh for security |

## Why this exists

I'm finishing my B.S. in Cybersecurity at WGU and looking for SOC and infrastructure roles. The way I learn is to run things, so I built the lab I'd want to put in front of a hiring manager. The configs run on my actual cluster, not in a sandbox, and they catch real things.

If you're hiring and want to see what I'd run, this is it.

## What this isn't

Not affiliated with Wazuh or any vendor. Not a packaged product. Don't clone it and run on your network expecting plug-and-play. These configs assume the topology of my homelab and you'd need to adapt.

Heavyweight artifacts like the full Ansible role library are at [infra-roles-public](https://github.com/sjviklabs/infra-roles-public).

## Related

I write up the parts of this that generalise. The free
[SOC Interview Cheat Sheet](https://sjviklabs.com/cheatsheet?utm_source=github&utm_medium=referral&utm_campaign=soc_interview&utm_content=repo_readme) is the
quick-reference set, and the
[SOC Analyst Interview Kit](https://sjviklabs.com/soc-interview-kit?utm_source=github&utm_medium=referral&utm_campaign=soc_interview&utm_content=repo_readme) is the
longer preparation system built around the same triage workflow this lab runs.

The repo is the evidence and stands on its own. The guides are optional.

## License

MIT. Use what's useful.
