 # Linux 

 > Command + Option + Arguments

  ### List 

  `cat file.txt`

  `cat -n abc.txt`  , `n` for line number

  ### Calender

  `ncal` , calender current month

  `ncal july 2025`
  option are case sensitive

  ### Manual Pages

  `man cat`

  `man ls`

  `man ncal`

  ### Folder 

  `pwd` , present working directory

  `cd` , change directory

  `mkdir` , create directory

  `cd /` , root directory

  `cd ~` , home directory

  `cd /home/amresh/Documents`, absolute path(actual path)

  `cd Documents` , Relative to home

  ### List

  `ls -l` , long format

  `ls -h` , human readable form

  ### Remove
   
   `rm abc.txt`, remove file

   `rm myDir` , error , myDir is dir

   `rm -d myDir`, remove MyDir empty directory

   `rm -r myDir`, remove recursive MyDir  directory

### Copy & Move

  `cp ./file ./mylocation/`, copy file

  `mv ./file ./mylocation/`, move file

### Indirection

  `cat a.txt b.txt > c.txt`  , `a`,`b` data combine and output add in `c.txt`

  `cat a.txt >> c.txt`, append (no overwrite)

  ```sh
  cat > abc.txt
  Hello I am Amresh Maurya
  # Press Ctrl + D, then 'your enterted data write in abc.txt.'
  ```

  ### Statistics
  
  `stats abc.txt` , detailed statistics

  `file abc.txt`, to get file type

  ### Timestamps

  `ls -lc`, long format + change time

  `ls -lu`, last access time

  `ls -l`, long format + (default modification time)

  ### File System Parition
  
  `df ` , file system partition

  `df -h ` , file system partition in GB

  ### Process

  `ps `, process

  `ps a` , all process

  `ps -ef`

  `ps -aux`

  ### Update Password

  `sudo passwd`, update password

  `su root`,

  `mlocate` , package

  ```sh
  locate myfile # show all location of this file
  ```

### Grep (Global regular expression print)

`grep searchString fromThisFile`, default case-sensitive

` grep -i searchStr ThisFile` , -i for case in-sensitive

`grep -v jas ThisFile`,`jas` ko chorkar baki sab print karega 

`grep -e ThisSearch -e ThisAlso index.txt`, ye dono k liye search karega

`grep -n ThisSearch index.text`

### Shebang
`#!/bin/bash`, #! --> directive , /bin/bash --> path of binary


## Processes

Process ek running instance hai kisi program ka

Pprocess type - 

 - Foreground Processes - terminal me directly run hote hai
 - Background Processes - ye process terminal se alag run hoti hai, app `&` ka use krke process ko background me run kar saktey hai
  
### Process States
 - Running - actively CPU ko use kar raha h
 - Waiting - Process kisi resource or event ka wait kar rahi h 
 - Stopped - Process ko temporarily stop kar diya gaya hai
 - Zombie - Process khatam ho chuka hai, lekin parent process ko info nahi mili isliye abhi bhi system m hai.  


` ps ` , list down all current processes

` ps aux`, a-> all users ki process, u-> user oriented format, x-> daemon process ko bhi include kar leta h

`top`, `htop` , ye process ko status, memory usage dekh sakte hai

`kill PID` , process ko Khatam krne k liye
`kill -9 PID`, Forcefully terminate

`bg` , background me ek stopped process ko resume krne k liye

`bg %job-number`


`fg` , Background se ek process ko foreground me laane k liye

`fg %job-number`

fork() -> current process ka duplicate create karna
exec() -> ye new program ko current process ke context me load karta hai


> Daemon Process vo background process hoti h jo system start hone par run hoti hai aur system shutdown hone tak chalti hai.

> Everything in linux is a file, even processes ,

  /proc --> /proc file system for process into string


  ## Special Permission

  setuid(s), setgid(s), stickybit(t)

```sh 
  chmod u+s filename # setuid
```

```sh 
  chmod +t diretoryName # sticky bit
```
  
  > Numerical Representation of sticky bit = 1

  setgid numerical rep. = 2 
  setuid numerical rep. = 4

## Numeric Mode 
r == 4

w == 2
 
x == 1

`chmod 755 file.txt`, 755,owner,group,other
