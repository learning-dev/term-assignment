# Term-assignment

**Assignment given by the mentor to explain the given terms with minimum 2 lines.**


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

**8.** **git pull** : pull the changes from remote repo to local repo. It is required to pull before pushing to remote repo.

```bash
git pull # pull from remote repo.
```

**9.** **git cherry-pick** : choose a commit from another branch and add it your branch and commit. It takes commit **hash** i.e atleast 4 characters.

```bash
git cherry-pick 1cb2fG # cherry-pick commit with given hash
```

**10.** **git merge :** used to merge a given branch name to current branch. i.e all the changes (commits) from merged branch. This creates a new merge commit.

```bash
git merge another-branch # cherry-pick commit with given hash
```

## Explain Database

**Database** - It is an organized collection of data. Complex databases are developed using 'design and modelling' techniques.

## SQL Database

**SQL Database** - SQL stands for Structured Query language, used for query, manipulate and define data.  It is a relational database - a type of database that stores and datapoints access that are related to one another.

## NoSQL Database -

**NoSQL Database** - It is a non-relational database that does not require fixed schema, avoid joins and is easy to scale. Read is faster in case of NoSQL database. One such example would be MongoDB.


## 10 popular databases

**1. MySQL server** - It is a relational database. Most popular for web applications. It's a freeware, with frequent security and feature updates.

**2. PostGresSQL** - Relational Database, frequently used for web databases. Allows user to manage both structured and unstructured data. Can be hosted at number of enivronments.

**3. Microsoft SQL Server** - SQL database engine built by Microsoft. Works on both cloud-based servers and local servers. Provides features like dynamic data masking (only authorized users can see sensitive info). Ideal for organizations that use microsoft products. pricing wise only few organizations can afford.

**4. MongoDB** - non relational Database that supports JSON. Data of any structure can be stored and accessed quickly and easily. schema can be written without downtime.

**5. MariaDB** - originally forked from Mysql. It is highly compatible with MySql. gives variety of storage engines to choose from. Fairley new compared to Mysql DB.


**6.  SAP HANA** - database engine by SAP that is column-oriented and can handle SAP and non SAP data. Supports SQL. Pricing is high.

**7.  Oracle Database** - very first database engine to be developed and is relational. Oracle tends to set the bar for other databases. requires resources once installed. Pricing let's only few orgs use it.

**8.  DB2** - database developed by IBM, has NoSQL capabalities. It can read JSON and XML Files. Ideal for Large organizations.

**9. Cassandra** - NoSQL database engine by Apache, which is distributed, column wide store, with no single point of failure and high availability.

**10. Redis** - it is an open source database, with im-memory data structure store. Can be used database, cache and message broker.


## ACID

**ACID** refers to the four key properties of a transaction: atomicity, consistency, isolation, and durability.

- **Atomicity** : All changes to data are  performed as if they are a single operation. For example, in an application that transfers funds from one account to another, **the atomicity property ensures** that, if **a debit is made successfully from one account**, the **corresponding credit is made to the other account.**

- **Consistency** : Data is in consistent state when a 	transaction starts and when it ends.


- **Isolation** : the intermediate state of a transaction  is invisible  to other transations. As a result, transaction that run concurrently appear to be serialized.

- **Durability** : After a transaction successfully completes, changes to data persist and are not undone, even in the event of a system failure.

## Aggregations

**Aggregations** is a process in which a single entity alone is not able to make sense in relationship so the relationship of two entities acts as one entity.

for Example, Manager manages Project **or** Employees doesn't makes sense. He has to manage **both** employees and work on project too. so both, enties - project and employees defin the relationship with manager.


## Joins

**Joins** is a clause in SQL that lets  combine columns while querying the data. Joins correspond to operation in relational algebra. inner join, outer join, cross join are the types of joins.


## CAP Theorem

**CAP** theorem is a tool used to makes system designers aware of the trade-offs while designing networked shared-data systems.


 The theorem states that networked shared-data systems can only guarantee **two of** the following **three properties**:

- **Consistency** - A guarantee that every node in a distributed cluster returns the same, most recent, successful write. Consistency refers to every client having the same view of data.

- **Availabilty** - Every non-failing node returns a response for all read and write request in a resonable amount of time.


- **Partition Tolerant** - The system continues to function and upholds its consistency guarantees in spite of network partitions.

- So, it possible to have **two at a time** i.e. **CP (Consistent and Partition Tolerant)** or **CA Consistent and Available)** or **AP (Available and Partition Tolerant)**



## Normalization

It is the **process of reducing the redundancy of data** in the table and also **improving the data integrity**. There are various database normalization rules like 1NF, 2NF and so on.


## Database Sharding

**Sharding** is a database Architechture pattern related to horizontal partitioning -- **the practice of separating one table’s rows into multiple different tables, known as partitions.**

Each **partition has the same schema and columns**, but also **entirely different rows**.



## 7 network layers

- **Physical (Layer 1)**: responsible for **transmission and reception of unstructured raw data between device and physical trasmission medium**. Layers converts digital bits into electrical, radio or optical signals.

- **Data Link (Layer 2)** : The data link layer provides **node-to-node data transfer** - a link between two directly connected nodes. It **detects and possibly corrects errors** that may occur **in the physical layer.**

- **Network (Layer 3)**: layer provides the functional and procedural means of 	transferring variable length of data sequences (called packets) from one node to another connected in **different networks**.


- **Transport (Layer 4)** - layer provides the functional and procedural means of **transferring variable-length data sequences from a source to a destination host**, **while maintaining the quality of service functions**.

- **Session (Layer 5)** - layer controls  the connections between computers. It establishes, manages and terminates the connections between local and remote application.

- **Presentation (Layer 6)** -  layer provides independence from data representation by **translating between application and network formats.** The presentation layer **transforms data into the form that the application accepts.**

- **Application (Layer 7)** - layer closest to the **end user**, which means **both OSI application layer and user interact directly with software application.** This layer interacts with software applications that implement a communicating component.












