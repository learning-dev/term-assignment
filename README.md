# Term-assignment

**Assignment given by the mentor to explain the given terms with not more than 2 lines.**


## 10 popular commands - daily use

### touch command
- **touch** : It is used to modify the 'access time' & 'modification time'.  To modify only "access time" use "-a" option and to modify only "modification time" use "-m". If a **file doesn't exist** it creates a new file with that name. So, touch command **can be used to create a new file**.


```bash
touch filename #creates a new file, if doesn't exist
touch -a filename # modify only the access time
touch -m filename # modify only the modification time
touch -c filename # prevent creation of new file, if it doesn't exists
```


