
# <u>Week 1</u>
- #### Intro
	- `pwd` - present working directory
	- `ls` - list folder/files in the directory
	- `ps` - processes that are running in that particular shell
	- `uname` - current OS
	- Anatomy of command prompt![[Screenshot 2024-01-27 at 7.41.01 PM.png]]
	- `ls -a` lists all the hidden files too
	- `ls -l` lists in the long form
	- `man -ls` is the manual page for the `ls` command
	- File system hierarchy![[Screenshot 2024-01-27 at 7.45.39 PM.png]]
	- files in the root folder ![[Screenshot 2024-01-27 at 7.51.48 PM.png]] [[Screenshot 2024-01-27 at 7.56.39 PM.png]]
	- /bin: essential command binaries; sometimes a link to usr/bin
	- /boot: boot loader
	- /dev: every device that is connected to the computer is actually a file
	- /etc: configuration of various services w.r.t. to the particular machine
	- /lib: shared libraries and kernel modules
	- /media: folders which are created when you insert a removable device into the computer
	- /mnt: mount points; directories which are available to traverse the file system of the hardware
	- /opt: application software packages are installed
	- /run: data relevant for running processes
	- /sbin: executables meant for system administration are kept; essential system libraries
	- /srv: data for ftp or http services
	- /tmp: temporary files
	- /usr: secondary hierarchy![[Screenshot 2024-01-27 at 8.03.38 PM.png]]
	- /var: variable data such as log files for various system services running in the background![[Screenshot 2024-01-27 at 8.04.41 PM.png]]

- ### Simple commands
	- `date`: to know date and time
	- `cal`: calendar of a month
	- `free`: memory statistics
	- `groups`: groups to which user belongs
	- `file`: what type of a file is it?
	- Typical output of `ls -l` ![[Screenshot 2024-01-27 at 8.21.24 PM.png]]
	- ##### File types![[Screenshot 2024-01-27 at 8.24.03 PM.png]]
	- Permission string `r` for read ; `w` for write ; `x` for executable![[Screenshot 2024-01-27 at 8.27.20 PM.png]]Read(r):4 ; Write(w): 2 ; Execute(x): 1     ;   rw = 4+2=6   ;  wx = 2+1=3
	- `mkdir` create a new folder 
	- to change permissions
		- `chmod g-r <directory_name>` for group read permission
		- `chmod u-w <directory_name>` for user write permission
		- `chmod o-x <directory_name>` for others executable permission
		- `chmod 700 <directory_name>` will give read/write/executable for owner and no permission for group or others
	- `touch <file_name>` to create a new file
	- `cp <file_1> <file_2>` copies the first file into a new file by the name `file_2`
	- `mv file_2 ..` will move `file_2` to one level up
	- `mv file_2 file_2a` will change the name of `file_2` to `file_2a`
	- `rm <file_name>` to remove the file
	- `ls -li` will give the inode number
	- `ls -lia` will give the inode number with every file (even hidden ones)
	- `less <file_name>` lets you read a file page by page
	- some important commands![[Screenshot 2024-01-27 at 11.06.02 PM.png]]

# <u>Week 2</u>
- Multiple uses of `/` is as good as single `/`
- `ls`
	- Short and long forms of options
	- Interpretation of directory as an argument
	- Recursive listing
	- Order of options on command line
	- `ls -l <dir_name>` will show the list of files/directories within the `<folder_name>`
	- `ls -ld <dir_name>` will only give you the long-listing string (details) of `<folder_name>` and nothing more
	- `ls -l <dir> -di` $=$ `ls -d <dir> -li` $=$ `ls -i <dir> -ld` $=$ `ls <dir> -ldi` ; Order doesn't matter much
- #### Inspecting text files
	- `less <file>` : lets you read page by page
	- `cat <file>` : concatenate text on the screen; will dump the text and exit; you can't move back and forth in the file
	- `more <file>` : similar to `less`; page by page
	- `head <file>` : shows first 10 lines   ;  `head -n <number> <file>` : lets you read `<number>` first lines
	- `tail <file>` : shows last 10 lines   ;  `tail -n <number> <file>` : lets you read `<number>` last lines
	- `wc <file>`: shows how many lines lines, words, and bytes
- More commands
	- `which <command>` : will tell you where the command is located    ; e.g. `which less`
	- `whatis <command>`  : brief description of the command    ; e.g. `whatis less`
	- `apropos`  : for exploring new commands
		- `apropos who` : set of commands which'll help you to know who all are logged on
	- `help` will show certain keywords that are reserved for the shell which you're running
	- `type <command>` shows you the type of the command
	- `alias <name>='<command>'` will give the `<command>` an alias as `<name>`
		- `unalias <alias_name>` will remove an alias
- ##### Multiple arguments
	- <u>Options</u>: enhanced features of the command
	- <u>Argument</u>: specific name of the files/directories that we're giving on the command line so that the command acts on those respective files/directories
	- `touch <file1> <file2> <file3>` : all three files will be created together
	- `cp <file1> <file2>` : will copy `<file1>` to `<file2>` by overwriting the file
	- `rm -r <directory>`  : will delete the directory and its contents
	- Recursions
		- `cp` command doesn't assume recursions. While copying, it asks whether you want it to be recursive or not. To make it recursive: `cp -r` command is used
		- `mv` command assumes recursions
		- Some commands assumes recursions, some don't
- Links
	- <u>Symbolic Link</u>: `ln -s <source_dir> <destination_dir>` :  `<source_dir>` for which we're making the link and `<destination_dir>` is the link itself  ; both files will have different i-node numbers
	- <u>Hard Link</u>: `ln <source_dir> <destination_dir>` : creates a hard link  ; both files will have the same i-node number
- File sizes
	- `ls -s`
	- `stat`  : will show the exact size of the file
	- `du`  : will show the blocks taken up
	- Role of block size: files that are smaller than the block size take up the whole block
- In-memory filesystems
	- `/proc`
	- `/sys` 

- ## $hell variables
	- `echo`
		- command used for printing
		- can also print values of variables
		- `echo $USERNAME` = `echo $USER`  : gives the username
		- `echo $HOME` = `echo $PWD`  : gives present working directory
		- `echo $HOSTNAME`  : name of the machine
		- `printenv` = `env`  : gives a whole bunch of shell variables
		- `echo $PATH`  : shows list of directories that Shell looks up to identify where is a particular command located
	- every shell variable will start with a '$'
	- Special shell variables:
		- `$0`  : name of the shell
		- `$$`  : process ID of the shell
			- `ps`  : what are all the processes that are running right now
			- `ps --forest`  : indicates which process launched which child process
			- `ps -e`  : shows all the processes that are running in the operating system
			- `ps -f`  :  gives you the parent id
			- Process control
				- `&`  : to run a job in the background
				- `fg`  : to bring it to the foreground
				- `coproc`  : 
				- `jobs`  : to show all the processes that are running
				- `top`  : what are all the processes running, sorted in the decreasing usage of CPU
				- `kill`  : to kill a process
		- `$?`  : return code of previously run program
			- Exit code: (always has values between 0 and 255)
				- 0 : success
				- 1 : failure
				- 2 : misuse
				- 126 : command cannot be executed
				- 127 : command not found
				- 130 : processes killed using control+C
				- 137 : processes killed using kill -9 <\pid>
		- `$-`  : flags set in the bash shell
			- `h`  : locate and hash commands
			- `B`  : brace expansion enabled
			- `i`  : interactive mode
			- `m`  : job control enabled
			- `H`  : ! style history substitution enabled
			- `s`  : commands are read from stdin
			- `c`  : commands are read from arguments
	- ### Creating a variable
		- ## PPT Slides
			- to create a new shell variable![[Screenshot 2024-02-04 at 8.25.46 PM.png]]
			- Exporting a variable ![[Screenshot 2024-02-04 at 8.26.13 PM.png]]
			- Using variable values ![[Screenshot 2024-02-04 at 8.26.25 PM.png]]
			- Removing a variable or a value of a variable ![[Screenshot 2024-02-04 at 8.26.51 PM.png]]
			- Testing if a variable is available or not ![[Screenshot 2024-02-04 at 8.27.07 PM.png]] ![[Screenshot 2024-02-04 at 8.27.41 PM.png]]
			- Substitute a default value ![[Screenshot 2024-02-04 at 8.28.04 PM.png]]
			- Reset value if variable is set![[Screenshot 2024-02-04 at 8.28.42 PM.png]]
			- List of variable names: `echo ${!H*}`![[Screenshot 2024-02-04 at 8.29.28 PM.png]]
			- Length of string value![[Screenshot 2024-02-04 at 8.29.56 PM.png]]
			- Slice of string value ![[Screenshot 2024-02-04 at 8.30.31 PM.png]]
			- Remove matching pattern![[Screenshot 2024-02-04 at 8.30.56 PM.png]]
			- Keep matching pattern![[Screenshot 2024-02-04 at 8.31.44 PM.png]]
			- Replace matching pattern ![[Screenshot 2024-02-04 at 8.32.02 PM.png]]
			- Replace matching pattern by location ![[Screenshot 2024-02-04 at 8.32.24 PM.png]]
			- Change case ![[Screenshot 2024-02-04 at 8.32.45 PM.png]]
			- Restricting value types ![[Screenshot 2024-02-04 at 8.33.13 PM.png]]
			- Removing restrictions![[Screenshot 2024-02-04 at 8.33.45 PM.png]]
			- Indexed arrays![[Screenshot 2024-02-04 at 8.34.35 PM.png]]
			- Associative arrays (index can be anything integers, strings, etc.)![[Screenshot 2024-02-04 at 8.35.56 PM.png]]
		- cannot start the name of a variable using a digit
		- `[[ -v <variable_name> ]];` and then followed by `echo $?` to  check if a variable exists
		- Parent shell can export a variable to a child shell `export $<variable>`. Any modifications to the variable in the child shell cannot be exported to the parent shell.
		- `mydate=date` with date in back quote will. This will give the value of the variable as the output of the `date` command, but doesn't change dynamically
			```shell
			mydate=`date`
			echo $mydate     # will display the date 
			
			myvar=`echo Sunday that is today`
			echo $myvar      # will display "Sunday that is today" 
			```
		- To give a default value to the variable
			```shell
			echo ${myvar:-hello}    # will display "hello" if the variable is not set
			echo ${myvar:=hello}    # will set "hello" to the variable if ISN'T set
			echo ${myvar:+hello}    # will set "hello" to the variable if IS set
			echo ${myvar:?"not set"}    # returns "not set" if variable isn't set
			```
		- To inspect what variables are present
			```shell
			printenv      # will display all the variables in memory
			echo ${!H*}   # will return all the variables starting with "H"
			```
		- Length of a the value of the variable
			```shell
			echo ${#<var_name>}   # will return 0 if variable is doesn't exist
			```
		- Variable string slicing
			```shell
			mydate=`date`
			echo ${mydate:6:10}   # starting from 7th char, will display 10 characters
			echo ${mydate: -3:3}   # starting from 3rd last char, will display 3 chars
			```
		- Pattern matching
			```shell
			myvar=filename.txt.jpg
			echo ${myvar#*.}  # return "txt.jpg"
			echo ${myvar##*.}  # return "jpg"
			
			myvar=filename.SomethingElse.jpeg
			echo ${myvar##*.}  # return "jpeg"    useful for knowing the extension of a file
			echo ${myvar%.*}  # return "filename.SomethingElse"
			echo ${myvar%%.*}  # return "filename"
			echo ${myvar%%.*}${myvar##*.}   # returns filenamejpeg
			echo ${myvar%%.*}.${myvar##*.}   # returns filename.jpeg
			
			echo ${myvar/e/E}    # will replace the first occurenc of "e" with "E"
			echo ${myvar//e/E}    # will replace all the occurences of "e" with "E"
			
			echo ${myvar/#M/m}   # if the string starts with "M", replace it with "m"
			echo ${myvar/#g/G}   # if the srting ends with "g", replace it with "G"
			```
		- Changing cases of the string
			```Shell
			mydate=`date`
			echo ${mydate,}   # will print with only the first letter as lowercase
			echo ${mydate,,}   # will print with all the letters as lowercase
			
			echo ${mydate^}   # will print with the first letter as uppercase
			echo ${mydate^^}   # will print with all the letter as uppercase
			```
		- Changing the restrictions on types or values of variables
			```shell
			declare -i mynum   # mynum should only have integers
			mynum=995
			echo $mynum  # will return "995"
			mynum=hello  
			echo $mynum  # will return "0"
			
			declare -l myvar  # for only lowercase letters
			myvar=hello
			echo $myvar      # will return "hello"
			myvar=AIrpLAnE
			echo $myvar      # will return "airplane"
			
			declare -u myvar # for only uppercase letters
			declare +u myvar # to remove the restriction
			
			today=`date`
			declare -r today   # makes the variable read-only
			declare +r today   # not possible
			```
		- Arrays
			```Shell
			declare -a myarr
			myarr[0]=Sunday    # insert "Sunday" at the 0th index
			myarr[1]=Monday    # insert "Monday" at the 1st index
			echo ${myarr[0]}   # returns "Sunday"
			echo ${#myarr[@]}  # returns the length of the array
			echo ${myarr[@]}   # displays all the elements of the array
			echo ${!myarr[@]}  # displays the indexes of the array
			unset 'myarr[0]'   # deletes the element at the 0th index
			myarr+=(Tuesday)   # appends "Tuesday" at the 2nd index
			myarr=(Sunday Monday Tuesday Wednesday)  # will populate the array in one go
			
			
			declare -A hasharr    # can use strings as indexes too
			hasharr[0]="Aman"
			hasharr[1]="Bimal"
			hash["mm12b001"]="Charlie"
			echo ${!hasharr[@]}
			```

- ## Linux process management
	- `sleep 3` will put the terminal to sleep for 3 seconds
	- `coproc sleep 5` will run the 'sleep' command in the background. You will still have access to the command prompt and the terminal will let you know when the process has been completed.
		- `help coproc` will give information on what `coproc` command does.
	```Shell
	coproc sleep 30  # will give a process ID and run the process in the background
	ps --forest      # can see the process running
	kill -9 <Process_ID> # will kill the process
	
	
	sleep 30 &    # will run the process in the background
	fg            # will bring the process to the foreground
	```
	- to kill a process: Ctrl+C if in the foreground OR `kill -9 <Process_ID>` in background or any other shell
	```Shell
	bash -c "echo \$-"    # launched a child shell which had only one action to do and then exit
	bash -c "echo \$-; ps --forest;"  # will show that the child shell launched ps command
	```
	- `history` command will give the history of all the commands that have been run
		- `!<command_ID>` will repeat that particular command
	- `echo {a..z}` will list all the alphabets
	- `echo *` gives you the list of all the files in the current directory
	- `echo D*` will list all the files starting with "D"
	- Multiple commands can be run in a single line by separating them with semicolon ";"


# <u>Week 3</u>
- #### Combining commands
	- `<command_1> ; <command_2> ; <command_3>`
		- commands executed one after the other irrespective of whether commands are successful or not 
	- `<command_1> && <command_2>`
		- second command runs <u>only if</u> the first command is successful
	- `<command_1> || <command_2`
		- second command <u>will not</u> be executed if the first command succeeds
	- `$BASH_SUBSHELL`
		```Shell
		(<command_1> ; <command_2> ; <command_3>)  # will run the commands in a subshell
		echo $BASH_SUBSHELL    # returns "0" will tell you which level of subshell you are in
		(echo $BASH_SUBSHELL)    # returns "1"
		```
- #### File descriptors and Redirections
	- `stdin` (0)  : pointer to the stream which is coming from the keyboard (user input)
	- `stdout` (1) and  `stderr` (2) : pointing to the screen where the display of the output is made
	- `<command> > file1`  : the output of the command is redacted to `file1` ; a new file will be created if `file1` doesn't exist, contents of `file1` will be overwritten ; throws error if you don't have write permission
	- `<command> >> file1`  : the output of the command is appended at the end of `file1`
	- `<command> 2> file1`  : redirects the `stderr` to `file1`; if no error, then `file1` is empty
	- `<command> < file1`  : takes input from the file instead of a keyboard
	- `<command> > file1 2>&1`  : stdout and stderr are both going to the same `file1`
	- `<command_1> | <command_2>`  :  stdout of the first command is the stdin for the second command
	- `<command_1> | <command_2> > file1`  : the final output will be written in `file1`
	- `<command> > file1 2> /dev/null`  : when you have confidence that there'll be no error; /dev/null used a bin
	- `command | tee file1`  : `tee` command splits stdout into 2 streams; one for file1 and a copy on the screen
		```Shell
		ls -1 /usr/bin > file1   # will create a file and write output of command in the file
		cat > file1   # because cat command wasn't given a file, it will take input from keyboard
		
		# command >> file1    # will append the output to the file 
		echo 'Hello World from the first command' > file1
		echo 'FROM the second command' >> file1
		
		ls /usr/bin | wc -l    # will tell you the number of lines in the output of ls /usr/bin
		
		ls $HOME | tee file1 file2   # will display the output and also write it to file1 and file2
		```
		![[Screenshot 2024-02-05 at 10.23.07 PM.png]]![[Screenshot 2024-02-05 at 10.24.31 PM.png]] ![[Screenshot 2024-02-05 at 10.58.21 PM.png]] ![[Screenshot 2024-02-05 at 11.05.31 PM.png]]

- ### Software Management
	- ##### Package manager
		- tools for installing, updating, removing, managing software
		- install new/updated software across network
		- Package — file look up, both ways
		- Database of packages on the system including versions
		- Dependency checking
		- Signature verification tools
		- Tools for building packages
		- Package types![[Screenshot 2024-02-06 at 10.47.27 PM.png]]For running linux server, you need familiarity with RPM
		- Architectures![[Screenshot 2024-02-06 at 10.50.06 PM.png]]Look out for the string which indicates the architecture for which the particular package has been built and also which architecture your desktop machine is. Usually, this is taken care by package manager.
		- Tools![[Screenshot 2024-02-06 at 10.52.20 PM.png]]
	- ##### Package management in Ubuntu using `apt`
		- Inquiring package db
			- `apt-cache search <keyword>`  : Search packages for a *keyword* 
				- `apt-cache search fortune` , `apt-cache search wget`
			- `apt-cache pkgnames`  : List all packages
				- `apt-cache pkgnames | sort | less`
				- `apt-cache pkgnames nm`  : will show packages that start with "nm"
			- `apt-cache show -a <package>`  : Display package records of a package
				- `apt-cache show nmap` will work the same as `apt-cache show -a nmap`
				- ![[Screenshot 2024-02-06 at 11.03.53 PM.png]]
	- ##### Package priorities
		- <u>required</u> : essential to proper functioning of the system
		- <u>important</u> : provides functionality that enables the system to run well
		- <u>standard</u> : included in a standard system installation
		- <u>optional</u> : can omit if you do not have enough storage
		- <u>extra</u> : could conflict with packages with higher priority, has specialised  requirements, install only if needed
	- Packages are belonged to sections. You can look at all the packages in a particular section by going to this [link](https://packages.ubuntu.com/focal/)
	- To verify the authenticity of a package installed, use checksums. 3 major ways checksums are computed
		1. md5sum (128bit)
		2. SHA1 (160bit)
		3. SHA256 (256bit) : the most advanced and the one used today
		```Shell
		echo "Hi this is the Checksum test" > file1.txt
		echo "Hi this isnt the Checksum test" > file2.txt
		
		md5sum file1.txt
		md5sum file2.txt  # the 128 bit string will be very different for both files
		
		sha1sum file1.txt
		sha1sum file2.txt  # the 160 bit string will be very different for both files
		
		sha256sum file1.txt
		sha256sum file2.txt  # the 256 bit string will be very different for both files
		```
	- Only sudoers can install/upgrade/remove packages
		- sudo — Super User do
		- `sudo cat /etc/sudoer`  : will show who all have super user privileges
	- When installing a package, system knows the website to download the package from. This information is stored in `/etc/apt`. Files : sources.list  Folder: sources.list.d
	- `sudo apt-get update` to get updates of packages and store in cache and then run `sudo apt-get upgrade` to install the package updates.
	- `sudo apt-get install <package>` to install a package
	- `sudo apt-get reinstall <package>` to reinstall package
	- Removing / cleaning up
		- `sudo apt autoremove`  : will remove the packages that are no longer required because newer updates have replaced them.
		- `sudo apt-get clean`  : clean local repository of retrieved package files
		- `sudo apt-get remove <package>`  : remove a package
		- `sudo apt-get purge <package>`  : purge package files from the system
	- ###### Package management in Ubuntu using `dpkg`
		- `/var/lib/dpkg`  : has info about the packages on your system
		- `dpkg -l <pattern>`  : list all packages whose names match the pattern
		- `dpkg -L <package>`  : list installed files that came from `<package>`
		- `dpkg -s <package>`  : report the status of `<package>`
		- `dpkg -S <pattern>`  : search installed packaged for a file
		- `dpkg-query -W -f='${Section} ${binary:Package}\n | sort | less`  : shows a list of all the sections and within each section what are all the binary packages that are installed on the system