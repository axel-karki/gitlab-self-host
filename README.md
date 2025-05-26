## GitLab Self-Hosted Setup

### What is GitLab?

**GitLab** is a complete DevOps platform that provides source code management (SCM), continuous integration/continuous delivery (CI/CD), issue tracking, and more — all in a single application. It enables teams to collaborate on code, automate pipelines, and manage the software development lifecycle efficiently.

---

### Why Self-Host GitLab?

Self-hosting GitLab gives you full control over:

* User access and authentication
* Data privacy and compliance
* Custom CI/CD runner configuration
* Integration with internal infrastructure

It is ideal for organizations requiring secure, private, or air-gapped environments.

---

## Installation

To install GitLab on a new VM, run the following playbook:

```bash
ansible-playbook playbooks/install_gitlab.yml
```

This playbook:

* Installs the GitLab CE (Community Edition) package
* Sets up necessary dependencies and configurations
* Starts the GitLab web interface and backend services

---

## Initial Setup

1. Access the UI using:
   ```
   ssh -i <ssh_file_path> -L 8080:<gitlab_vm_private_ip>:80 root@<server_public_ip>

3. To login for the first time:
   ```
   User: root
   Password: find here -> root@debian:~# cat /etc/gitlab/initial_root_password
   ```
   Find the password here and login as root
   <img width="739" alt="Screenshot 2025-05-26 at 7 22 47 AM" src="https://github.com/user-attachments/assets/f15fd596-5141-44af-912f-4910f419ce54" />

4. Navigate to Admin area. Crate a new user with admin privileges and configure an initial password. Use the account to login as admin. The root account can now be disabled.
   <img width="770" alt="Screenshot 2025-05-26 at 7 25 10 AM" src="https://github.com/user-attachments/assets/f814318a-b029-47f1-b9b7-ec93f02f7b09" />

5. Create Project
   <img width="770" alt="Screenshot 2025-05-26 at 8 08 59 AM" src="https://github.com/user-attachments/assets/a1ae1ce8-46be-465b-bde7-d268561da5d2" />

6. Runner to be configured
   <img width="724" alt="Screenshot 2025-05-26 at 8 09 11 AM" src="https://github.com/user-attachments/assets/98a5901a-3679-4893-837a-4cf67a1cddb2" />
   <img width="783" alt="Screenshot 2025-05-26 at 8 11 15 AM" src="https://github.com/user-attachments/assets/ec6f2980-80d6-4c29-b0bf-f8b10a4babe3" />
