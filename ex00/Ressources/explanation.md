level0 binary with exec rights of level1 (getfacl)

segfaults when no argument is given
when 1 is given it prints "No !\n" on stdout

gdb level0

disas main ->
eax is compared with 423 (0x1a7)
if equal, strdup, getegid, geteuid, setresgid, setresuid then execve
if not equal, jump to the fwrite

./level1 423 ->
opens a shell
whoami -> level1
we can open /home/user/level1/.pass and get the flag !

As for source file,
chmod u+x source.c (.c necessary for compilation)
chmox +wx ~
mv compiled_binary ~
you can execute it as level0 ! (and cat /home/... to get the flag)