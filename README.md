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
