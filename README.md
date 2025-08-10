# lsf-cluster-ykb (LSF Sample (YKB) Cluster With Ansible Automation)
Static LSF configuration and Ansible automation for cluster **ykb**.

## What is included
- Static LSF configs under `configs/ykb/` (lsb.*, lsf.conf, profile.lsf, install.config)
- Ansible playbooks and roles to:
  - Install LSF (`ansible/playbooks/install_lsf.yml`)
  - Deploy updated config (`ansible/playbooks/update_config.yml`)
  - Restart LSF daemons (`ansible/playbooks/restart_lsf.yml`)
- Ansible inventory with 2 masters and 20 slaves (`ansible/inventory/hosts.yml`)

## Quick usage
1. Edit any config files under `configs/ykb/` as required.
2. Commit & push to GitHub.
3. From a machine with Ansible and access to cluster hosts:
   - Install LSF (first time):
     ```bash
     ansible-playbook -i ansible/inventory/hosts.yml ansible/playbooks/install_lsf.yml
     ```
   - Deploy updated configuration (masters only):
     ```bash
     ansible-playbook -i ansible/inventory/hosts.yml ansible/playbooks/update_config.yml
     ```
   - Restart LSF daemons:
     ```bash
     ansible-playbook -i ansible/inventory/hosts.yml ansible/playbooks/restart_lsf.yml
     ```
