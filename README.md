Red Hat Ansible Automation Platform Deployment
==============================================

This collection of files provides a complete set of playbooks for deploying
Red Hat Ansible Automation Platform in your environment on hosts running
Red Hat Enterprise Linux.

For getting started with installation and setup instructions, please refer to:

- Install Guide -- https://access.redhat.com/documentation/en-us/red_hat_ansible_automation_platform/2.4/html-single/red_hat_ansible_automation_platform_installation_guide/index

## 🚀 Custom Setup Instructions

### Prerequisites
- RHEL 8 or 9 system
- Valid Red Hat subscription
- Minimum 4GB RAM, 20GB disk space
- Root or sudo access

### Quick Start
1. **Copy the inventory template**:
   ```bash
   cp inventory.template inventory
   ```

2. **Edit the inventory file**:
   - Replace `CHANGE_THIS_PASSWORD` with strong passwords
   - Replace `YOUR_REDHAT_USERNAME` with your Red Hat Customer Portal username
   - Replace `YOUR_REDHAT_PASSWORD` with your Red Hat Customer Portal password
   - Update the hostname in the `[automationcontroller]` section

3. **Run the setup**:
   ```bash
   sudo ./setup.sh
   ```

### Access After Installation
- **Web Interface**: `https://your-hostname`
- **Username**: `admin`
- **Password**: Value set in `admin_password` in inventory

### ⚠️ Security Notes
**NEVER commit the following files to version control:**
- `inventory` (contains passwords and credentials)
- `*.log` files
- SSL certificates and keys
- Any files containing sensitive information

### Troubleshooting
1. **Check logs**: `sudo tail -f setup.log`
2. **Verify services**: `sudo systemctl status nginx automation-controller`
3. **DNS/SSL issues**: Ensure hostname resolves correctly
4. **Firewall**: Open ports 80, 443, 27199

