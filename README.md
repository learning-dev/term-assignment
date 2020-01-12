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