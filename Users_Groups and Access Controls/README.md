# Users_Groups and Access Controls
## Exercises
### Setup ssh login using authorized keys. Try changing mode for this file and find ways to debug failed logins
Create SSH keys
```
$ ssh-keygen
```
Copying public key using `ssh-copy-id`
```
ssh-copy-id username@remote_host
```
Authenticating using SSH keys
```
ssh -i id_rsa username@remote_host  # id_rsa using private key
```