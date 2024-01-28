# Reverse Proxy Setup

This Ansible playbook sets up an Nginx reverse proxy server at the specified
host. The reverse proxy server acts as an entry point into a Tailscale network
and proxies web traffic to a specified Tailnet host/port. These configurations
are intended for use with an OpenBSD host server.

## Prerequisites
- OpenBSD server running at specified host name
- Password-authenticated root user accessible on SSH port 22
- If running on macOS: install `passlib` and `bcrypt==3.2.2` via pip

## Playbooks
- `bootstrap`: Run on first-time set up for SSH user/port and firewall configs
- `main`: Set up system and reverse proxy (can be run multiple times)

## Ansible Vault Secrets
Edit secrets using `ansible-vault edit group_vars/vault.yml`. The host is set
up under the `vault` group and inherits these variables.
