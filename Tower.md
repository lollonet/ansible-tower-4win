# Impostazioni di Ansible Tower

# Impostazione del Project
SCM type: Git

SCM URL: https://github.com/lollonet/ansible-tower-4win.git

Check *Update Revision on Launch*

# Impostazione degli Inventoryies
Creare un inventory per la VM Windows con le vars come da esempio.

*ansible_connection: winrm*

*ansible_winrm_transport: basic*

*ansible_winrm_server_cert_validation: ignore*

*ansible_user: windowsuser*

*ansible_password: "passw0rd"*

*ansible_host: 192.168.56.3*

Creare un inventory per host linux impostando le vars:

*ansible_user: linuxuser*

*ansible_password: "passw0rd"*

# Workflow

Creare un Job Template per ogni playbook esistente.

Definire un workflow che lancia il Job template contenente il playbook win-defragscript-async.yaml.
Definire il lancio di altro Job Template su termine JOB ok (launch-linux-job.yaml) o failed (Demo Job Template)

In questo caso la logica del flusso è definita all'interno del workflow ansible.
E’ comunque possibile che il processo Windows lanciato da win-defragscript-async.yaml lanci l’esecuzione di un ulteriore Job Template o Workflow tramite API call, passandogli se è necessario, alcuni paramteri.
