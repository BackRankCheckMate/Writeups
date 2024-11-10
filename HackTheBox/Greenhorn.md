# User flag

Nmap the ip 

We find a few ports open

Append the ip and greenhorn.htb in hosts file, open the ip in a browser

We have an admin page, asking for a pass

Take a look at port 3000

Goto Explore, we have a git repo kind of site

Take a look at login.php

We find that the pass is in /data/settings/pass.php

Decode the pass, we get the password for the admin panel found previously

Enter the admin dashboard

We find that the plucks version is 4.7.18

We find CVE-2023-50564

Clone the repo, customize it and run the poc file

Listen using nc

We get shell access

We already have the password of junior(same as login.php), su junior

We get the user flag

# Root flag

Now run python server in the target machine

Use wget to download the pdf file in local machine

We have a pdf file, where the password is pixelated

Use depix to reverse the pixels

We find the password to root

su root

We find the root flag
