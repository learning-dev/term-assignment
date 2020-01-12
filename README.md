# Term-assignment

**Assignment given by the mentor to explain the given terms with not more than 2 lines.**


## 10 popular commands - daily use

**1.** **touch** : It is used to modify the 'access time' & 'modification time'.  To modify only "access time" use "-a" option and to modify only "modification time" use "-m". If a **file doesn't exist** it creates a new file with that name. So, touch command **can be used to create a new file**.


```bash
touch filename #creates a new file, if doesn't exist
touch -a filename # modify only the access time
touch -m filename # modify only the modification time
touch -c filename # prevent creation of new file, if it doesn't exists
```

**2.** **mkdir** : It is used to create a new "directory" (folder).  you can pass in **-p** option to create whole path, if the parent folder doesn't exists.

```bash
mkdir foldername # creates a new folder/directory
mkdir -p parentfolder/childfolder # create folder 'parentfolder' if it doesn't exits.
```
**3.** **cd** : cd (change directory ) is used to switch between directories. **cd ..** will take you to one directory up. **cd -** will take you previous directory that you came from. **~** represents home directory. So, **cd ~** will take you to **home** directory.

```bash
# consider structure ~/homework/math/, you are in ~(home)
cd homework # get into homework folder
cd math # get into math folder
cd .. # go one directory up i.e. homework
cd - # takes you to last directory you were in i.e. math
```
**4.** **rm** : It is a command to remove file and folder. Once the file is deleted. you cannot easily recover the file. To remove folders you can -d option. To delete the **write protected** files it will ask for you prompt and to avoid prompt use **-f** option and to delete files recursively use **-r** option. Use option **-i** for prompt to appear before delete a file.

**NOTE:** **NEVER** use ```rm -rf``` in home directory with **ROOT** permissions.
```bash
# delete using rm command
rm homework.md # delete the file
rm file.txt file2.txt  # delete multiple files.
rm -i fib.py  # to ask before deleting. (prompt) hit 'y' to delete
rm -d folder # delete folders
rm -rf node_modules # delete files recursively and force fully
```
**5.** **mv** : It is used to move files and rename files. You can move multiples files to directory. to move files/folders you have first specify **source** and then **destination**. you can take backup before overwriting a files using -b option.

```bash
mv source_folder destination_folder # move the folder to a new folder
mv oldname.txt newname.txt  # rename using mv command
mv file1.txt file3.txt file2.txt dest_folder  # move multiple files to a folder.
mv file1.txt another_folder/file1.txt # overwrite to a file.
mv -b file1.txt file2.txt # backup of file1.txt will created before overwriting(renaming) to file2.txt
mv  -S .bak -b file1.txt file2.txt # -S to specify the extension of the backup file that you want.

```

**6.** **ls** : used to list the files and directories in the current directory.  **-a** lists all the files and folder i.e. hidden files and folder too. **-h** lists file sizes in human readable format. **-F** appends **/** at the end of the directories. **-R** lists files recursively inside all sub-directories (returns a very long list). **-ltr** option will list latest files first.  **-S** list files according to size in descending order.

```bash
ls  # lists files and folders inside the current folder
ls -l  # list files and folder with size, permission and other details
ls -a server_files  # list all (including hidden ones) files and folder in the given folder
ls  -lh # -h option will display size in human readable form.
ls -F  # appends "/" at the end of folder names while listing
ls  -R  # -R list all the files and folders inside the "sub-directories" inside the current folder.
ls -ltr # lists all the files in reverse time order (latest first) -r option to display in reverse.
ls -lS # -S with l with display size in descending order(biggest first)
```
**7.** **cp**: used to copy files and folder. Use **-R** option to copy directory to another directory.  cp takes **source** and **destination** file/folder as arguments. use **--preserve** option lets you preserve the file attributes like permissions, groups and user ownerships. **-v** prints out the files being copied currently to the stdout. **-b** Option to create backups before overwriting. **-i** option to ask before overwrite.

```bash
cp -R source_folder destination_folder # copy the source folder to a destination folder
cp oldfile.txt anotherfile.txt  # copy using cp command
cp -i file1.txt file3.txt  # ask before overwrite a file, hit y to proceed .
cp -v file1.txt another_folder/file1.txt # display which file is being copied now.
cp -b file1.txt file2.txt # backup of file1.txt will created before overwriting(renaming) to file2.txt
cp  -S .bak -b file1.txt file2.txt # -S to specify the extension of the backup file that you want.

```

**8.** **pwd**: displays the current working directory. **-P** option shows the physical links rather than symbolic links


```bash
pwd  # display the (whole path) current working directory.
/home/mohammed/.zsh # output

pwd -P  # Shows the physical location rather symbolic link
/home/mohammed/dotfiles/zsh

```

**9.** **cat**: used to display the contents of the file, concatinate files and redirect the ouput of the file.

```bash
cat file1.txt # displays the content of the file stdout(terminal)
cat file1.txt file2.txt > file3.txt  # moves the contents file1.txt & file2.txt to new file3.txt
cat file1.txt file3.txt >> file2.txt  # concat the file1.txt file3.txt an "existing" file3.
cat file1.txt file1.txt | sort > file3.txt # combine both files and sort the content in alphabetically and store to file3.txt.

```

**10.** **nano**: It is a light-weight text editor. nano "filename" to open a file. **ctrl + o** to save and **ctrl + x** to exit.

```bash
nano file1.txt # open the file in the nano editor.
```

## 10 popular OS commands

**1.** **clear**: used to clear the terminal screen, you can access the previous content by scrolling up.

```bash
clear  # clear the terminal screen
```
**2.** **sudo**: stands for "SuperUser Do". Lets you run any command with Admin (super User) privileges. **Think twice before, running rm -rf with sudo**

 ```bash
sudo sh run_package.sh  # run script with super user privileges.
```
**3.** **history**: it gives you the list of  previous 500 commands (number depends on your config) ran in your terminal.


```bash
history  # list 500 previous commands
history 25 # list 25 previous commands
histroy | tail # list 25 previous commands
```

**4.** **tar**: it is used to compress and uncompress files. It supports formats like tar, tar.gz and tar.bz2. **-c** lets you create compressed file. **-x**, for uncompressing the file. It requires a **f** paramater to pass the file.

```bash
tar -cvf source_file.tar /home/source_file  # -c :create file, v-verbose, f- filename - create a source_file in current directory
tar -cvzf source_file.tar /home/source_file # create gz file using z option

tar -xvf file.tar  # extract the file. notice -x to extract

tar -tvf test_file.tar.gz # list the files in zip.

```

**5.** **uname**: show the information about the system your Linux/unix distro is running. **uname -a** prints the information like kernel release date, version, processor type, etc.

```bash
uname   # just the distribution name
uname -a  # kernel release date, version, processor type, etc.
```

**6.** **chmod**: chmod is used to change the permissions of the file. you can change using octal values and using ugo (user, group others) + permission( rx or just x). Octal values are **4 - read**, **2 - write**, **1 - execute**. So, we take the combination for read, write and execute 7. We take the sum of the values for each group

```bash
chmod 754 run_package.sh   # user = 7 (rwx), group= 5(rx) & others = read (r)
chmod + x run_package.sh # add executable permission to all i.e ugo

chmod u+x run_package.sh # add execution perm to only user.

chmod u=rwx, g=rx, 	o=r run_package.sh #another way of giving permissions.
```

**7.** **hostname**: It display the hostname. hostname -f newhostname to change the hostname (sudo perm required.). Paramters differ for mac and linux

```bash
hostname  # display hostname

sudo hostname -f newhostname

hostname -s # display shortname, if any

```

**8.** **top**: It displays all currently-running processes and their owners, memory usage, and lots of other details.

```bash
top  # display process detail
```

**9.** **echo**: echo command is used to display the contents of evironment variables and display the passed text. echo * will work as ls command. echo can be used to fill in the text into a file.

```bash
echo $PATH  # display Path env
echo * # works as ls command
echo some random line # displays 'some random line'
echo insert your line > test.txt # write term 'insert your line' to test.txt
```

**10.** **head**: shows the first 10 lines of the file. with option **-n** no-of-lines will display the required lines. you pass in multiples files too.

```bash
head test.txt  # display first 10 lines
head -n 20 test.txt # display first 20 lines
head test.txt config.txt # display 10 lines each from these files with headers to specify.
```


## 10 Popular Network Commands


**1.** **ping** : sends ICMP (Internet Control Protocol) echo request packages to the destination IP (server). You can use it check if you internet is workign or the remote destination is working.

```bash
ping 8.8.8.8 # ping google dns to check if you internet is working
ping your-website.com # to check if your server is up or not.
```

**2.** **ping** : sends ICMP (Internet Control Protocol) echo request packages to the destination IP (server). You can use it check if you internet is workign or the remote destination is working.

```bash
ping 8.8.8.8 # ping google dns to check if you internet is working
ping your-website.com # to check if your server is up or not.
```
**3.** **traceroute** : It is used to trace the route taken to network host.

```bash
traceroute facebook.com   # trace the route taken to reach the domain facebook.com
```

**4.** **nslookup** : used to query the Internet domain name servers. nslookup domain-name.com, checks if given domain name exists or not.

```bash
nslookup i-made-thatup.com  # checks if the domain exists or not
"** server can't find i-made-thatup.com: NXDOMAIN" # output
```

**5.** **netstat** : allows you a simple way to review each of your network connections and open sockets. It is helpful while performing web server troubleshooting.

```bash
netstat # displays protocol, ports information
```

**6.** **scp** : allows you to copy files to and from another host in the network. This is useful **when you are deploying application to you webserver.**. **-c** to enable compression and **6** forces scp to use IPv6. **4** forces to scp to use IPv4.

```bash
scp $configure.sh user@targethost:/$path
```

**7.** **w** : prints the summary of the current activity on the sysmtem, which includes **what each user is doing, and their process** plus **list all logged in users and system load for 1, 5 and 15 minutes**

```bash
w # display information

22:06  up 4 days, 26 mins, 6 users, load averages: 1.87 1.67 1.62
USER     TTY      FROM              LOGIN@  IDLE WHAT
mohammed console  -                Wed21   4days -
mohammed s000     -                Fri14   1day  -zsh
mohammed s001     -                Wed22   27:36 node /Users/mohammed/Documents
mohammed s002     -                Sat11   27:00 -zsh
mohammed s003     -                Sat18       - w
mohammed s004     -                21:46       3 -zsh
```
**8.** **whois** : displays whois information about the given domain-name like registrar, name servers and so on

```bash
whois google.com
```

**9.** **tcpdump** : allows you to capture and analyze network traffic going through your system. Often used to help troubleshoot network issues, as well security tool.

```bash
sudo tcpdump -D # lists the interfaces available for capture.
sudo tcpdump -i any # start capturing packets
```

**10.** **wget** : used to downloading files from internet. It supports downloading multiples files, download resume and limiting bandwidth used for downloads.

```bash
wget http://archlinux.mirrors.uk2.net/iso/2016.09.03/archlinux-2016.09.03-dual.iso # download the iso files
wget -c http://archlinux.mirrors.uk2.net/iso/2016.09.03/archlinux-2016.09.03-dual.iso # resumes download if started again at same directory.
```

## 10 Popular GIT Commands

**1.** **git init** : creates an empty git reposistory or reinitializes an existing one. There is ".git" folder created in the initialized directory.


```bash
git init # initilize a git repo.

```

**2.** **git add** : add files to staging area before committing. git add **filename** to file staging area. **-u** option adds the change of the tracked files and not the changes of new file (unstaged). **-A** option adds all changes to staging area (including new files i.e. unstaged).


```bash
git add server.py # add server.py to staging area.
git add -u # add changes of staged files only, ignore new files

git add -A # add all changes including new files and deletion of files.
```
**3.** **git status** : shows the status of the tree like **files in staging area**, **unstaged files**, **untracked files** and also **commits behind or forward by remote origin**. **-s** shows the status in short form.


```bash
git status # shows the status of working tree
git status -s # show in short form
git status --show-stash # show status of stash as well.
```
**4.** **git push** : push the files to remote repository. **-u** option to set upstream. **-f** push the files by force i.e by overwriting the refs.

```bash
git push # push the files remote repo
git push -u origin master # set the upstream to master branch of origin
git push -f # push files to remote repo by force i.e. overwriting refs
```

**5.** **git reset** : remove the files from staging area.  if you specify filename or multiple files then, it removes those files from staging area. **--hard** option removes files from staging area and discards the changes made after the last commit.


```bash
git reset # removes files from staging area.
git reset  server.py # remove server.py from staging area.
git reset --hard server.py # remove server.py from staging area and discard all changes after prevous commit.
```

**6.** **git commit** : commit the changes in the staging area. it takes **-m** takes a commit message. It opens a nano/vi editor to add a commit message.


```bash
git commit -m 'commit message' # commit
git commit  # opens your default git text editor to add msg
```

**7.** **git stash** : adds your changes (staged and unstaged) to stash and gives you clean working directory.  **--save** option takes a name to save with. **apply** option applies the changes from the stash stack i.e. on the top of stack. **list** options lists all the stash in the stack.


```bash
git stash # stash all the changes to stash 'stack'
git stash --save 'fix: incorrect followr count' # save to stash with a name
git stash list # list all the stash saved in the stack

git stash apply # apply the changes from the stash to the working directory (a stash from top of the stack) when no stash-name is given.
```


