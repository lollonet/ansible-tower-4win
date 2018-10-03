# Impostazioni di Ansible Tower

# Impostazione del Project
SCM type: Git
SCM URL: https://github.com/lollonet/ansible-tower-4win.git
Check *Update Revision on Launch*

# Impostazione degli Inventoryies
Creare un inventory per la VM Windows con le vars come da esempio.
ansible_connection: winrm
ansible_winrm_transport: basic
ansible_winrm_server_cert_validation: ignore
ansible_user: claudio
ansible_password: "pfa:12.ppf"
ansible_host: 192.168.56.3

# Creare un inventory per host linux impostando le vars:
ansible_user: linuxuser
ansible_password: "passw0rd"
