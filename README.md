# Linux Shell commands cheat sheet #

<br />
<br />

<div itemscope>
<h2 align=center
    tabindex=1
    itemprop="heading"
> 
Example commands 
</h2>
</div>

Command | Description
---|---|
date | print or set the system date and time
cal | display a caldendar
df | report file system space usage
free | display amount of free used memory in system
exit | ends terminal session


<div itemscope>
<h2 align=center
    tabindex=1
    itemprop="heading"
> 
Navigation 
</h2>
</div>

<br />

Command | Description
---|---|
pwd | print name of current/working directory
cd | change the working directory
ls | list directory contents

<br />

E.g. commands with options and arguments

```
ls -lth --reverse -S
```
* **-l**  :display results in long format
* **-t**  :sort by modification time
* **-h**  :display file sizes in human-readble format rather then in bytes
* **-S**  :sort results by file size
* **--reverse**  :displays the result in reverse order


<br />

<div itemscope>
<h2 align=center
    tabindex=1
    itemprop="heading"
> 
Exploring the file system 
</h2>
</div>

<br />

Command | Description
---|---|
file | determine file type
less | opposite of more

E,g. commands with options and arguments

```
[me@linuxbox ˜]$ file picture.jpg
picture.jpg: JPEG image data, JFIF standard 1.01
```

Using **less** :

Command | Description
---|---|
page up or b | scroll back one page
page down or spacebar | scroll forware one page
Up Arrow | Scroll up one line
Down Arrow | Scroll down one line
G | Move to the end of the text line
1G or g | Move to the beginning of the text file
n | search for the next occurrence of the previous search
q | Quit **less**

***less is more!!*** - from a class of programs called *pagers* allowing easy viewing of long text documents in a page-by-page manner.

<br />

<div itemscope>
<h2 align=center
    tabindex=1
    itemprop="heading"
> 
Linux file system structure
</h2>
</div>

<br />

Directory/File | Comment
---|---|
/ |root directory
/bin | contains binaries that must be present for the system to boot and run
/boot | contains the linux kernel, initial RAM disk image
/boot/grub/grub.conf | - menu.lst (boot loader)
/boot/vmlinuz | the kernel
/dev | device nodes - everything is a file, kernal maintains a list of all devices it understands
/etc | system-wide configuration files, shell scripts starting system services at boot time
/etc/crontab | file defining when automated jobs will run
/etc/fstab | a table of storage devices and their associated mount points
/etc/passwd | list of user accounts
/home | user home directory
/lib | shared library files used by core system programs. Similar to DLLs in Windows
/lost+found | used for partial recovery from corruption event.
/media | mount points for removable media
/mnt | contains mount points for removable devices mounted manually
/opt | used to install optional software, commercial products 
/proc | virtual filesystem maintained by linux kernel, looking glass to kernal itself
/root | home dir for root
/sbin | system binaries, programs performing vital tasks reserved to superuser
/tmp | intended for temporary files storage
/usr | likely largest dir, contains programs and support files used by regular users
/usr/bin | exec programs installed by linux distribution
/usr/lib | shared libraries for /usr/bin programs
/usr/local | system wide usable programs, install by system administrators
/usr/sbin | more system administration programs
/usr/share | contains all the shared data used by programs in /usr/bin. Config files,icons,screen backgrounds
/usr/share/doc | documentation folder
/var | dynamic directory(content). Databases, spool files, user mail
/var/log | contains log files, viewed by superuser e.g /var/log/messages

<br />

<div itemscope>
<h2 align=center
    tabindex=1
    itemprop="heading"
> 
Manipulating files and directories
</h2>
</div>

<br />


Command | Description
---|---|
cp | copy files and directories
mv | move (rename) files
mkdir | make directories
rm | remove files or directories
ln | make links between files

<br />

E.g. command description

<br />

```
mkdir directory...
mkdir dir1
mkdir dir1 dir2 dir3
```
```
cp item1 item2
cp item.. directory
```
```
mv item1 item2
mv item... directory
```

```
ln file link
ln -s item link
```

* **-i**  :propmts the user for confirmation, interactive
* **-u**  :performs operation only if either file/directory doesn't exist, or is newer
* **-v**  :displays informative messages as the move is performed
* **-r**  :with copy recursively copies directories and their contents


<br />

<div itemscope>
<h2 align=center
    tabindex=1
    itemprop="heading"
> 
Working with Commands
</h2>
</div>

<br />


type -- indicate how a command name is interpreted
which -- display which executable program will be executed
man -- display a command's manual page
apropos -- display a list of appropriate commands
info -- display commands' info entry
whatis -- description of a command
alias -- create alias for a command

type cmd -- displays description for program type: an executable command, command built into a shell type, a shell function, an alias
man program sections:
    -- 1 user commands
    -- 2 programming interfaces for kernel calls
    -- 3 program interfaces to the C library
    -- 4 special files sucas as devices nodes and drives
    -- 5 file formats
    -- 6 games and amusements such as screensavers
    -- 7 miscellaneous
    -- 8 system administrator commands
    e.g. man 5 passwd

apropos floppy
whatis ls 
info
    -- ? displays command help
    -- page up/ backspace displays previous help
    -- page down or spacebar display next page
    -- n Next - displays next node
    -- p Previous - display the previous node
    -- u Up - displays de parent node of the current diplayed node, usually a menu
    -- enter follow the hyperlink at the cursor location
    -- q Quit

composing commands with semi colons

e.g. cd /usr; ls; cd -;

<br />

<div itemscope>
<h2 align=center
    tabindex=1
    itemprop="heading"
> 
Redirection
</h2>
</div>

<br />


cat -- Concatenation files
sort -- Sort lines of text
uniq -- Report or omit repeated lines
wc -- Print newline, word, and byte counts for each file
grep -- Print lines matching a pattern
head -- Output the first part of a file
tail -- Output the last part of file
tee -- Read from standard input and write to standard output and files


redirection from standard output

ls -l file.text
ls -l > file.txt
> file.txt -- clear a file


shell file descriptors:
0 - standard input
1 - standard output
2 - standard error 

2> redirect from stderr
2>&1 redirect from file descriptor 2 (stderr) to 1(stdout)