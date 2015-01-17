# GPG
GPG is a wonderful open source and very commonly used key based encryption tool.

### Creating a key pair

So the first thing that you'll need to do before you begin encrypting and decrypting anything is create your key pair. This consists of your publickey and privatekey.

##### Getting to a terminal

`{ insert instructions on getting to a terminal here }`

The first think that you'll need to do is open a terminal and run

`gpg --gen-key`

##### Choosing a key type

This will prompt you with a question asking what kind of key you want.

```bash
Please select what kind of key you want:
   (1) RSA and RSA (default)
   (2) DSA and Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
```

`{ insert discussion of RSA and DSA here }` but for now let's choose RSA and RSA. So type `1` and hit return.

##### Choosing a key size

Choosing a key size can often times be a confusing task. The larger the key size the more secure your key but depending on what device you are using, the action of encrypting and decrypting using a larger key may cause performance impacts that you do not want to deal with. With most modern laptops and desktops this shouldn't be a problem so `4096` or `8192` (if offered) should be fine to use.

So when prompted with the message

```bash
RSA keys may be between 1024 and 8192 bits long.
What keysize do you want? (2048)
```
Feel free to reply with any size that you feel fits your need.

For more information there is this [fantastic explanation](http://danielpocock.com/rsa-key-sizes-2048-or-4096-bits) of the pros and cons between 2048 and 4096 length keys.


##### When should your key expire?

This is largely dependent on how you plan to use a key. The important thing to note is that since your key [can be renewed](http://madduck.net/blog/2006.06.20:expiring-gpg/) it doesn't really provide much (if any) security benefit.

So when prompted with

```bash
lease specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
```

Feel free to enter `0` if you want your key to last forever. We will go over revoking your privatekey if you have become compromsed later.

##### Basic Info

This is pretty self explanatory. Name, email and comment describing the key. I like to include my online handle (Nolski) and some words describing the machine I'm using it on (ex. *Nolski - Laptop Personal*)

##### Choosing a password

This is important
## References
[http://security.stackexchange.com/questions/5096/rsa-vs-dsa-for-ssh-authentication-keys#answer-5100](http://security.stackexchange.com/questions/5096/rsa-vs-dsa-for-ssh-authentication-keys#answer-5100)

[http://danielpocock.com/rsa-key-sizes-2048-or-4096-bits](http://danielpocock.com/rsa-key-sizes-2048-or-4096-bits)

[http://madduck.net/blog/2006.06.20:expiring-gpg/](http://madduck.net/blog/2006.06.20:expiring-gpg/)
