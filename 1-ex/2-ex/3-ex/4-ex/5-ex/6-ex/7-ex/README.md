# Review the Vault Agent Config file


1. While you are already ssh to Vault server

2. Issue the commands
 
``` cd /tmp
    cat agent-config.hcl```
 
pid_file = "./pidfile"

vault {
   address = "http://127.0.0.1:8200"
}

auto_auth {
   method "approle" {
       mount_path = "auth/approle"
       config = {
           role_id_file_path = "roleID"
           secret_id_file_path = "secretID"
           remove_secret_id_file_after_reading = false
       }
   }

   sink "file" {
       config = {
           path = "approleToken"
       }
   }
}

template {
  source      = "./certs.tmpl"
  destination = "./certs.json"
  #command = "bash updt.sh"
}

template {
    source = "./https.tmpl"
    destination = "./https.json"
}
```
ubuntu@ip-10-0-0-100:/tmp$ 

   ![alt text](../../../../../../../images/hcl.png)

[GoTo Next Exercise-8](8-ex)

[GoBack](../README.md)
