# dev-server-build
This repo documents build and hardening of the dev server supporting this GitHub portfolio.

Using Ansible to provision security conscious infrastructure as code

- Manual bootstrap - installed ansible (would be scripted for prod)
- FQCNs not used in these playbooks (only core modules, more easily human readable)
- Secrets live in /etc/ansible/secrets/dev-server-build-secrets.yml
- Initial hardening (harden.yml) - restricts remote root, creates ansible user (least privilege principle) - for production: scoped sudo and SSH from control node, here: unrestricted sudo, local exec only
- Harden using USG (harden-with-usg.yml) for Enterprise - CIS Level 1 benchmark via Ubuntu Pro. Audit/Fix split to prevent accidental hardening
- Harden without USG (harden-without-usg.yml) for non-Enterprise - UFW, SSH, Fail2Ban, unattended upgrades. Ansible-lockdown referenced for comprehensive prod alternative

Next steps:
- Packages/config to support portfolio
