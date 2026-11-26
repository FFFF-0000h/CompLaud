1. `echo $SHELL` - `/usr/bin/bash`
2. `ps -p $$ -o pid,ppid,comm ` - `PID (126025)  PPID (126008) COMMAND (bash)`
3. `which ls` - `/usr/bin/ls`
4. `file $(which ls)` - `/usr/bin/ls: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=d6281af586ce362d9c1029002636397df0cf21f1, for GNU/Linux 4.4.0, stripped`
5. `ls -l /proc/$$/fd` - `total 0
lrwx------ 1 username hostname 64 Nov 26 13:52 0 -> /dev/pts/1
lrwx------ 1 username hostname 64 Nov 26 13:52 1 -> /dev/pts/1
lrwx------ 1 username hostname 64 Nov 26 13:52 2 -> /dev/pts/1
lrwx------ 1 username hostname 64 Nov 26 13:52 255 -> /dev/pts/1`
6. `ls /nonexistent 1>/dev/null` - `ls: cannot access '/nonexistent': No such file or directory`
7. `ls /nonexistent > out.txt 2>&1` vs `ls /nonexistent 2>&1 > out.txt` - The order matters, note the one that puts the error in `out.txt` is the command on the L.H.S.
8. `man 2 open | head -40` -  To view a syscall page
