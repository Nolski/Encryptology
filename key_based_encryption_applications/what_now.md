# What now?

So now you have created your key pair. Great! GPG has exited and you have both a publickey and privatekey stored somewhere on your computer. Great! Now you can begin decryping and encrypting messages.

###The Key Chain

So before you can encrypt a message to someone you need their *publickey*. When you encrypt a message using their publickey, they can use their privatekey to decrypt it. Same when they try to contact you. They encrypt it with your publickey and you decrypt it with your privatekey.

That's why you can put your publickey online for anyone to use but you must keep your privatekey safe.

##### Viewing your key chain

To see what keys that you have access to for encrypting files you will want to list the publickeys in your key chain. You can do this with the `list-keys` command.

```
gpg --list-keys
```

##### Exporting a publickey (Giving this to others.)

For someone to be able to encrypt messages to you, they must have access to your publickey. Since you may have multiple publickeys that you want to export, you must provide the email address associated with it. In this case lets say the email address is `example@gmail.com`.

```
gpg --armor --export example@gmail.org
```
This should output some text such as:
```
-----BEGIN PGP PUBLIC KEY BLOCK-----
Version: GnuPG v0.9.7 (GNU/Linux)
Comment: For info see http://www.gnupg.org

[...]
-----END PGP PUBLIC KEY BLOCK-----
```

If you want your key to be stored in a file you can use the `--output` flag.

##### Importing a publickey

Importing a publickey is fairly easy once you have the other users key (let's say it's stored in a file called `bob.gpg` and has email `bob@gmail.com` associated with it), simply run:

```
gpg --import bob.gpg
```

This should produce some output that looks similar to:

```
gpg: key 9E98BC16: public key imported
gpg: Total number processed: 1
gpg:               imported: 1
```

Now if you list your keys again you should now see both your key and Bob's key.

```
gpg --list-keys
...
---------------------------------------
pub  1024D/BB7576AC 1999-06-04 Example (This is you) <example@gmail.com>
sub  1024g/78E9A8FA 1999-06-04

pub  1024D/9E98BC16 1999-06-04 Bob (This is Bob) <bob@gmail.com>
sub  1024g/5C8CBD41 1999-06-04
```

### Encrypting

Once you have the desired user in your keychain encrypting data that you wish to send them is fairly simple.

First, in your command line environment navigate to the item which you wish to encrypt. In this case lets say that I have a text file named `msg.txt` and I want to send it to `bob@gmail.com` (Lets also assume that I have already added Bob's publickey to my keychain). In the end we want to have an encrypted file by the name of `encryptedmsg.gpg`.

`gpg --output encryptedmsg.gpg --encrypt --recipient bob@gmail.com msg.txt`

###### Let's examine this command

`gpg` - This is fairly simple. This is the name of the program we are executing.

`--output encryptedmsg.gpg` - This flag sets the name of the output file (our encrypted file).

`--encrypt` - This tells GPG that we are encrypting.

`--recipient bob@gmail.com` - This is the user whos' publickey we are using to encrypt the message.

`msg.txt` - This is the file that we are encrypting.

So in general the calling of gpg works like this:
```bash
gpg [flags] [filename_to_encrypt]
```

Pretty simple right? It's a lot to remember but I'll write up a little cheat sheet that will make using gpg cake.

### Decrypting

Decrypting is fairly simple. You just need to pass the `--decrypt` flag. So lets say you want to decrypt `encryptedmsg.gpg`, all you need to do is run:
```
gpg --decrypt encryptedmsg.gpg
```

## References
[https://www.gnupg.org/gph/en/manual/x110.html](https://www.gnupg.org/gph/en/manual/x110.html)

[https://www.gnupg.org/gph/en/manual/x56.html](https://www.gnupg.org/gph/en/manual/x56.html)
