# chmod, change mode(permissions)

## Context: 

1 - POSIX files have permissions for owner(user), group, other to read, write, or execute.

2 - In Unix-like environments, files which start with . are known as dotfiles and are treated in some ways as 'hidden'. For example, the ls command by default does not list them. An example of a dotfile is a .gitignore file.

3 - ```ls -la``` lists current working directory's files including all hidden files(-a) and in the long list format(-l)

4 - The 10 char file permissions string. The first char denotes if it is a file(-) or directory(d) and each set of three chars after it are the read(r), write(w) and execution(x), three sets of three chars for user/owner(u), group(g), and other(o)
```
trevorstahl@Mac chmod_temp % ls -la
total 0
drwxr-xr-x   3 trevorstahl  staff    96 Jul  5 14:59 .
drwxr-x---+ 53 trevorstahl  staff  1696 Jul  5 14:59 ..
-rw-r--r--   1 trevorstahl  staff     0 Jul  5 14:59 somet.txt
trevorstahl@Mac chmod_temp %
```
-rw-r--r--, first char - means file, and user can read and write, group can read, other can read,


## Basic Usages:

```chmod u-x some.xyz``` change mode, user loses execution, on file some.xyz

```chmod g+r any.txt``` change mode, group gets read, on any.txt

```chmod o-rw note.txt``` change mode, others lose read and write, on note.txt

```chmod u=rw,go=r new_document.odt``` change mode, set user to only read and write, set group and other to only read, on new_document.odt

```chmod a=r only_read.txt``` change mode, set all(a) to only read, on only_read.txt



## Alternative Usages:

```chmod 777 script.py``` change mode, give read, write and execute to owner, group, others, on script.py
* Quick blanket fix for denied permisions on files, ***major security risk***, gives maximum permisions to everyone
* Uses octal binary in decimal to represent permissions for each group, binary:001 is 1 in decimal, 010 is 2, 011 is 3, 100 is 4, 101 is 5, 110 is 6, and 111 is 7. Each binary digit 001(1), 010(2), 100(4) represent execution, write, and read permissions. 111 which is 7 mean read, write, and execute.


## Examples:

```
trevorstahl@Mac chmod_temp % chmod 777 somet.txt 
trevorstahl@Mac chmod_temp % ls -l               
total 0
-rwxrwxrwx  1 trevorstahl  staff  0 Jul  5 14:59 somet.txt
trevorstahl@Mac chmod_temp % chmod a=rw somet.txt 
trevorstahl@Mac chmod_temp % ls -l               
total 0
-rw-rw-rw-  1 trevorstahl  staff  0 Jul  5 14:59 somet.txt
trevorstahl@Mac chmod_temp % chmod ugo=r somet.txt 
trevorstahl@Mac chmod_temp % ls -l                
total 0
-r--r--r--  1 trevorstahl  staff  0 Jul  5 14:59 somet.txt
trevorstahl@Mac chmod_temp % chmod a-r somet.txt
trevorstahl@Mac chmod_temp % ls -l              
total 0
----------  1 trevorstahl  staff  0 Jul  5 14:59 somet.txt
trevorstahl@Mac chmod_temp % 
```
