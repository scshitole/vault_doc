# Login into the Vault Server


1. Open the Web Shell if not open  and login to udf/udf

2. Change the directory ```cd bigip-vault```

3. Run ```terraform output``` if you don't see the ssh details of ubuntu

   ![alt text](../../../../../images/ssh1.png)

4. Run ```vault status``` you will see this error 

``` Error checking seal status: Get "https://127.0.0.1:8200/v1/sys/seal-status": http: server gave HTTP response to HTTPS client```

5. Now Configure the following
```export VAULT_ADDR=http://127.0.0.1:8200```
then do 
```vault status```
Key             Value
---             -----
Seal Type       shamir
Initialized     true
Sealed          false
Total Shares    1
Threshold       1
Version         1.5.0
Cluster Name    vault-cluster-1e807b0d
Cluster ID      6ae06394-1e80-8e5f-8e07-ae356446daa3
HA Enabled      false
ubuntu@ip-10-0-0-100:~$ ```


   ![alt text](../../../../../images/ssh2.png)


[GoTo Next Exercise-6](6-ex)

[GoBack](../README.md)
