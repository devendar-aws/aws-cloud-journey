# Day 1 – Linux Basics on EC2

## Commands Practiced:
pwd, ls, cd, mkdir, touch, echo, nano, rm, rmdir, cp, mv, cat, chmod, sudo, apt update, apt install, clear

chmod XXX - Owner Group Others
7 - 4+2+1 (Read, Write, Execute)
6 - 4+2+0 (Read, Write)
5 - 4+0+1 (Read, Execute)
4 - 4+0+0 (Read)
3 - 0+2+1 (Write, Execute)
2 - 0+2+0 (Write)
1 - 0+0+1 (Execute)

read - r, write - w, execute - x

chmod 400 
4 - r-- only read to Owner
0 - --- no permission to Group
0 - --- no permission to Group

chmod 755
7 - rwx Read, Write, Execute to Owner
5 - r-x Read, Execute to Group
5 - r-x Read, Execute to Group


sudo -i "file.pem"
"Identity file" — tells ssh to use the private key to authenticate


## Output:
Namaste from EC2!

## Screenshot:
[terminal showing Linux shell](day4/linux-on-ec2.png)
