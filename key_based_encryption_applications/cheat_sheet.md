# Cheat Sheet

| Action | GPG Command |
| -- | -- |
| Store encrypted message in plaintext | `--armor` |
| Encrypt message | `gpg --encrypt --recipient  <user-email>`|
| Decrypt message | `gpg --decrypt` |
| Name output file | `--output <filename>`|


### Examples

Encrypting a file to `bob@gmail.com` [TODO: Expand upon this scenario]
```
gpg --output encryptedmsg.gpg --encrypt --recipient bob@gmail.com msg.txt
```

Decrypting a file `encryptedmsg.gpg` that was encrypted for you.
```
gpg --output undecryptedmsg --decrypt encryptedmsg.gpg
```

