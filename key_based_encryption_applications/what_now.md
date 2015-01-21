# What now?

So now you have created your key pair. Great! GPG has exited and you have both a publickey and privatekey stored somewhere on your computer. Great! Now you can begin decryping and encrypting messages.

###The Key Chain

So before you can encrypt a message to someone you need their *publickey*. When you encrypt a message using their publickey, they can use their privatekey to decrypt it. Same when they try to contact you. They encrypt it with your publickey and you decrypt it with your privatekey.

That's why you can put your publickey online for anyone to use but you must keep your privatekey safe.

To be continued..

### Now onto the encryption process

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

## References
[https://www.gnupg.org/gph/en/manual/x110.html](https://www.gnupg.org/gph/en/manual/x110.html)
