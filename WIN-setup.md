# Setup Windows Machine

https://docs.ansible.com/ansible/2.7/user_guide/windows_setup.html#winrm-setup


In inventory file definire la macchina windows e le sue variabili:

windows:
hosts:
win10vm:
vars:
ansible_user: claudio
ansible_host: 192.168.56.3
ansible_password: "pfa:12.ppf"
ansible_connection: winrm
ansible_winrm_transport: basic
ansible_winrm_server_cert_validation: ignore



set-executionpolicy (in windows) con lo script in
https://raw.githubusercontent.com/ansible/ansible/devel/examples/scripts/ConfigureRemotingForAnsible.ps1

Controllare con
winrm enumerate winrm/config/Listener
