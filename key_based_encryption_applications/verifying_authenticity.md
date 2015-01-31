# Verifying authenticity

So here is a situation for you. You receive a publickey from your friend over the internet but you aren't quite sure of the publickey's authenticity. Have your friend contact you through a means which you are sure it is them and have them give you the key's fingerprint. Then use gpg to verify the key using the fingerprint.

```
gpg --fingerprint
```
This should give you a message that looks like
```
pub  1024D/9E98BC16 1999-06-04 Example (Example) <example@gmail.com>
    Fingerprint: 268F 448F CCD7 AF34 183E  52D8 9BDE 1A08 9E98 BC16
```

TODO
