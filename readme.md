### Encrypt
`openssl enc -aes-256-cbc -salt -in setup.sh -out enc_setup.enc -pbkdf2 -iter 100000`

### Decrypt
`openssl enc -d -aes-256-cbc -salt -in enc_setup.enc -out setup.sh -pbkdf2 -iter 100000`

### Single liner download + decrypt
`wget -O ./enc_setup.enc https://github.com/mrjackwills/setup/raw/main/enc_setup.enc ; openssl enc -d -aes-256-cbc -salt -in enc_setup.enc -out setup.sh -pbkdf2 -iter 100000`

### Cloud-init 
```yaml
#cloud-config
 runcmd:
   - wget -O /root/setup.enc https://github.com/mrjackwills/setup/raw/main/enc_setup.enc
```
