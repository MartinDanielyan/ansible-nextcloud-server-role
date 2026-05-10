# ansible-nextcloud-server

An Ansible role to deploy **Nextcloud** behind an **Nginx** reverse proxy on CentOS/RHEL systems.

## Features
* Automated Nextcloud installation and configuration.
* PHP-FPM optimization for Nextcloud.
* Nginx configuration with SSL support.

## Prerequisites
* **Operating System:** CentOS/RHEL 7 or 8.
* **Database:** A pre-configured MySQL/MariaDB instance is required.
* **Ansible:** 2.9 or higher.

## Role Variables
You can find these in `defaults/main.yml`:
* `nextcloud_version`: The version of Nextcloud to install (Default: `latest`).
* `ssl_cert_path`: Destination path for SSL certificates.

## SSL Configuration
To enable SSL, place your certificate and key in the `files/` directory.
Update the certificate filenames in the playbook variables or `defaults/main.yml` to match your domain (e.g., `yourdomain.com.crt`).

## Usage Example

### 1. Inventory (`inventory.yml`)
```yaml
[centos]
nextcloud_server ansible_host=192.168.88.235 ansible_user=deploy

```

## 2. Instalation (`install-nextcloud.yml`)
```yaml

  - hosts: centos
    gather_facts: yes
	become: yes

    roles:
      - nextcloud

```
