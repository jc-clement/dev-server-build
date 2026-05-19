# dev-server-build
This repo documents build and hardening of the dev server supporting this GitHub portfolio.

Using Ansible to provision security conscious infrastructure as code

- Manual bootstrap - installed ansible (would be scripted for prod)
- FQCNs not use in these playbooks (only core modules, more easily human readable)
- Secrets live in /etc/ansible/secrets/dev-server-build-secrets.yml
- Initial hardening (harden.yml) - restricts remote root, creates ansible user (least privilege principle) - for production: scoped sudo and SSH from control node, here: unrestricted sudo, local exec only

Next step
- harden-with-USG.yml (Enterprise)
- harden-without-USG.yml (non-Enterprise)
