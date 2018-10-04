# Some ansible playbooks and scripts #

# win-defrag-async.yaml #
Semplice playbook per il lancio del defrag su Windows. Utilizza il modulo win_defrag. Utile per verificare il funzionamente di win_rm.
Controlla il risultato il modo asincrono.

# win-defragscript-async.yaml
Semplice playbook per il lancio del defrag su Windows. Utilizza il modulo win_shell ed esegue uno script Power Powershell (defrag.ps1).
Controlla il risultato il modo asincrono.
Customizzare il path per il proprio ambiente.

# launch-linux-job.yaml
Semplice playbook per il lancio di una shell su host linux che ospita la VM di Tower. La shell esegue una find. Customizzare per il proprio ambiente.


# defrag.ps1
Powershell script. Lancia un defrag sul disco locale. Alla fine chiama una API di Tower, tramite curl POST, lanciando un Job Template diverso in caso di esecuzione corretta o meno.
Impostare il corretto numero del JOb Template da lanciare all'interno della URL chiamata dalla CURL.
Impostare le credenziali corrette.

# test-scripts/windows-hosts.ini
Esempio di inventory con variabili per impostare win_rm. Customizzare per il proprio ambiente.

# debug_msg.yaml
Esempio di playbook che utilizza una variabile passata al lancio del Job Template.
La variabile va inserita nel payload della richiesta HTTP POST specificando il Content-type in maniera coerente.

Ad esempio:

curl -H 'Content-Type: application/json;charset=UTF-8' -d '{"extra_vars": {"var_message": "parametro_1"}}' -k -u admin:xwuRhHfAnfqU  https://10.42.0.42/api/v2/job_templates/12/launch/

In alternativa si possono scrivere le variabili in un file JSON da passare all'opzione "-d" tramite "@".
Ad esempio:
curl -H 'Content-Type: application/json;charset=UTF-8' -d '@c:\path\to\file.json' -k -u admin:xwuRhHfAnfqU  https://10.42.0.42/api/v2/job_templates/12/launch/
