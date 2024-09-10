
# <u>Week 1</u>
- #### Intro
	- `pwd` - present working directory
	- `ls` - list folder/files in the directory
	- `ps` - processes that are running in that particular shell
	- `uname` - current OS
	- Anatomy of command prompt![[Screenshot 2024-01-27 at 7.41.01 PM.png]]
	- `ls -a` lists all the hidden files too
	- `ls -l` lists in the long form
	- `man -ls` is the manual page for the `ls` command
	- File system hierarchy![[Screenshot 2024-01-27 at 7.45.39 PM.png]]
	- files in the root folder ![[Screenshot 2024-01-27 at 7.51.48 PM.png]]![[Screenshot 2024-01-27 at 7.56.39 PM.png]]
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
	- /usr: secondary hierarchy![[Screenshot 2024-01-27 at 8.03.38 PM.png]]
	- /var: variable data such as log files for various system services running in the background![[Screenshot 2024-01-27 at 8.04.41 PM.png]]

- ### Simple commands
	- `date`: to know date and time
	- `cal`: calendar of a month
	- `free`: memory statistics
	- `groups`: groups to which user belongs
	- `file`: what type of a file is it?
	- Typical output of `ls -l` ![[Screenshot 2024-01-27 at 8.21.24 PM.png]]
	- ##### File types![[Screenshot 2024-01-27 at 8.24.03 PM.png]]
	- Permission string `r` for read ; `w` for write ; `x` for executable![[Screenshot 2024-01-27 at 8.27.20 PM.png]]Read(r):4 ; Write(w): 2 ; Execute(x): 1     ;   rw = 4+2=6   ;  wx = 2+1=3
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
	- some important commands![[Screenshot 2024-01-27 at 11.06.02 PM.png]]

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
			- to create a new shell variable![[Screenshot 2024-02-04 at 8.25.46 PM.png]]
			- Exporting a variable ![[Screenshot 2024-02-04 at 8.26.13 PM.png]]
			- Using variable values ![[Screenshot 2024-02-04 at 8.26.25 PM.png]]
			- Removing a variable or a value of a variable ![[Screenshot 2024-02-04 at 8.26.51 PM.png]]
			- Testing if a variable is available or not ![[Screenshot 2024-02-04 at 8.27.07 PM.png]] ![[Screenshot 2024-02-04 at 8.27.41 PM.png]]
			- Substitute a default value ![[Screenshot 2024-02-04 at 8.28.04 PM.png]]
			- Reset value if variable is set![[Screenshot 2024-02-04 at 8.28.42 PM.png]]
			- List of variable names: `echo ${!H*}`![[Screenshot 2024-02-04 at 8.29.28 PM.png]]
			- Length of string value![[Screenshot 2024-02-04 at 8.29.56 PM.png]]
			- Slice of string value ![[Screenshot 2024-02-04 at 8.30.31 PM.png]]
			- Remove matching pattern![[Screenshot 2024-02-04 at 8.30.56 PM.png]]
			- Keep matching pattern![[Screenshot 2024-02-04 at 8.31.44 PM.png]]
			- Replace matching pattern ![[Screenshot 2024-02-04 at 8.32.02 PM.png]]
			- Replace matching pattern by location ![[Screenshot 2024-02-04 at 8.32.24 PM.png]]
			- Change case ![[Screenshot 2024-02-04 at 8.32.45 PM.png]]
			- Restricting value types ![[Screenshot 2024-02-04 at 8.33.13 PM.png]]
			- Removing restrictions![[Screenshot 2024-02-04 at 8.33.45 PM.png]]
			- Indexed arrays![[Screenshot 2024-02-04 at 8.34.35 PM.png]]
			- Associative arrays (index can be anything integers, strings, etc.)![[Screenshot 2024-02-04 at 8.35.56 PM.png]]
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
		![[Screenshot 2024-02-05 at 10.23.07 PM.png]]![[Screenshot 2024-02-05 at 10.24.31 PM.png]] ![[Screenshot 2024-02-05 at 10.58.21 PM.png]] ![[Screenshot 2024-02-05 at 11.05.31 PM.png]]

- ### Software Management
	- ##### Package manager
		- tools for installing, updating, removing, managing software
		- install new/updated software across network
		- Package — file look up, both ways
		- Database of packages on the system including versions
		- Dependency checking
		- Signature verification tools
		- Tools for building packages
		- Package types![[Screenshot 2024-02-06 at 10.47.27 PM.png]]For running linux server, you need familiarity with RPM
		- Architectures![[Screenshot 2024-02-06 at 10.50.06 PM.png]]Look out for the string which indicates the architecture for which the particular package has been built and also which architecture your desktop machine is. Usually, this is taken care by package manager.
		- Tools![[Screenshot 2024-02-06 at 10.52.20 PM.png]]
	- ##### Package management in Ubuntu using `apt`
		- Inquiring package db
			- `apt-cache search <keyword>`  : Search packages for a *keyword* 
				- `apt-cache search fortune` , `apt-cache search wget`
			- `apt-cache pkgnames`  : List all packages
				- `apt-cache pkgnames | sort | less`
				- `apt-cache pkgnames nm`  : will show packages that start with "nm"
			- `apt-cache show -a <package>`  : Display package records of a package
				- `apt-cache show nmap` will work the same as `apt-cache show -a nmap`
				- ![[Screenshot 2024-02-06 at 11.03.53 PM.png]]
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

# <u>Week 4</u>
- #### Pattern matching
	- ##### Regex
		- a pattern template to filter text
		- BRE: POSIX Basic Regular Expression engine
		- ERE: POSIX Extended Regular Expression engine
	- Usage
		- `grep <pattern> filename`  : each line in the file will be processed using the pattern provided
		- `command | grep <pattern>`  : every line in the output will be processed using the pattern provided
		- default engine: BRE
		- Switch to ERE: `egrep <pattern> filename` or `grep -E <pattern> filename`
	- Special characters (BRE & ERE)
		- `.`  : Any single character except null or newline
		- `*`  : 0 or more of the preceding character
		- `[]`  : any of the enclosed characters; hyphen (-) indicates character range
		- `^`  : anchor for beginning of line or negation of enclosed characters
		- `$`  : anchor for end of line
		- `\`  : escape special characters
	- Special character (BRE)
		- `\{n,m\}`  : Range of occurrences of preceding pattern at least `n` and utmost `m` times
		- `\(\)`  : grouping of regular expressions
	- Special character (ERE)
		- `{n,m}`  : Range of occurrences of preceding pattern at least `n` and utmost `m` times
		- `()`  : grouping of regular expressions
		- `+`  : one or more of preceding character/expression
		- `?`  : 0 or one of preceding character/expressions
		- `|`  : logical OR over the patterns
	- Character classes ![[Screenshot 2024-02-18 at 12.30.43 PM.png]]
	- Backreferences
		- `\1` through `\9`
		- `\n` matches whatever was matched by `n`th earlier parenthesised subexpression
		- `\(hello\).*\1`  : A line with two occurrences of 'hello'
	- BRE operator precedence ![[Screenshot 2024-02-18 at 12.34.24 PM.png]]
	- ERE operator precedence ![[Screenshot 2024-02-18 at 12.34.58 PM.png]]
	- Code practice
		- `grep 'Raman' filename`  : will only show lines with 'Raman' in them
		- `cat filename | grep 'Raman'`  : will return the same output as the one above
		- `cat filename | grep 'am$'`  : will return lines ending with 'am'
		- `cat filename | grep 'am\b'`  : will return lines with words ending with 'am'
		- `dpkg-query -W -f'${Section} ${binary:{Package}\n`  : will show all package names in a list form
		- `dpkg-query -W -f'${Section} ${binary:{Package}\n | egrep ' .{4}$'`  : shows all the package names which have exactly 4 characters
		- `cat filename | grep '[[:alpha:]]`  : any line with alphabetical character(s)
		- `cat filename | grep '[[:alnum:]]`  : any line with alpha-numerical character(s)
		- `egrep '[[:digit:]]{12}' patterns.txt`  : lines with 12 digits
		- `egrep '\b[[:digit:]]{12}\b' patterns.txt`  : lines with a 6 digit number
	- Text can be trimmed from top to bottom using the `head` and the `tail` commands. Horizontal trimming can be done using the `cut` command.
		- `cut -c 1-4 filename`  : will give the first 4 characters of each line
		- `cat filename | cut -d " " -f 1`  : delimiter as 'space'. Characters are separated using the 'space' and the first part is shown.
		- `cat filename | cut -d "," -f 2`  : comma as the delimiter
		- `cat filename | cut -d ";" -f 1 | cut -d "," -f 1`  : the text between ";" and ","

- ### Command Line Editors
	- Types of editors. Terminal Editors are more popular because they're more visual in nature. ![[Screenshot 2024-02-18 at 2.58.50 PM.png]]
	- Features:
		- scrolling, view mode, current position in file
		- navigation
		- insert, replace, delete
		- cut-copy-paste
		- search-replace
		- language-aware syntax highlighting 
		- key-maps, init scripts, macros
		- plugins
	- ###### "ed" editor commands![[Screenshot 2024-02-18 at 3.03.23 PM.png]]
		- `ed filename`  : will open the file in the editor
		- `P`  : wil open the prompt
		- `1`  : will show the first line
		- `$`  : will show the last line
		- `,p`  : content of the entire file
		- `2,3p`  : 2nd to 3rd line
		- `/pattern/`  : search of this pattern and the first occurrence of that pattern
		- `+`  : next line
		- `-`  : previous line
		- `r !date`  : will read output of the command in the buffer
		- `w`  : the buffer will be written into the file
		- `.d`  : to delete the line
		- `a`  : to append text
		- `s/pattern/new_pattern/`  : to change the `pattern` in the line to `new_pattern`
		- `f`  : which file is being edited
		- `p`  : which line is being edited
		- `5,6j`  : will join the 5th and the 6th line
		- `m0`  : move the current line to 0th position
		- `%s/\(.*\)/PREFIX \1/`  : every line will have 'PREFIX' at the beginning of it
		- `3,5s/PREFIX/prefix/`  : will substitute 'PREFIX' with 'prefix' in the 3rd to 5th lines
	- when invoking 'pico', it is actually opening 'nano'
	- ##### Nano editor
		- `nano filename`  : to open the file in nano visual editor
		- features of the nano editor ![[Screenshot 2024-02-18 at 5.11.15 PM.png]]![[Screenshot 2024-02-18 at 5.11.56 PM.png]]
	- ### vi editor
		- vi help![[Screenshot 2024-02-18 at 5.39.04 PM.png]]
		- vi command mode ![[Screenshot 2024-02-18 at 5.40.31 PM.png]] ![[Screenshot 2024-02-18 at 5.41.24 PM.png]] ![[Screenshot 2024-02-18 at 5.42.07 PM.png]]
		- `i`  : enter into 'insert' mode
		- `dw`  : delete the word
		- `:se nu`  : will show numbers for each line
			- `se nonu`  : to hide the line numbers
		- `3yy`  : will copy 3 lines
		- `p`  : paste the copied lines
		- `:1,5s/line/LINE/`  : will replace the first occurrence of the word 'line' with 'LINE' in the lines 1 to 5
			- `:1,5s/line/LINE/g`  : will replace the all the occurrences in the specified lines
		- `:%s/hello/hola/g`  : all 'hello' will be replaced with 'hola'

# <u>Week 5</u>
- ### scripts
	- awk and sed are included in Linux. Combining them with bash scripts is an attractive proposition. ![[Screenshot 2024-02-20 at 7.54.28 PM.png]]
	- Categories of shell scripts![[Screenshot 2024-02-20 at 7.56.12 PM.png]]Every script that is supposed to be sourced can also be executed. The difference lies in the syntax of execution and the Process ID
	- Script location
		- Use absolute path or relative path 
		- keep the script in folder listed in `$PATH`
		- Watch out for the sequence of directories in `$PATH`
	- bash environment
		- Login shell
			- `/etc/profile`
			- `~/.bash_profile`
			- `~/.bash_login`
			- `~/.profile`
		- Non-Login shell
			- `/etc/bash.bashrc`
			- `~/.bashrc`
	- output from shell scripts
		- `echo`  : simple ; terminated with a newline if `-n` option not given
			- `echo My home is $HOME`
		- `printf`  : supports format specifiers like in C
			- `printf "My home is %s\n" $HOME`
	- Input to shell scripts
		- `read var`  : user input into variables
	- ##### Shell Script arguments  `./myscript.sh -l arg2 -v arg4`
		- `$0`  : name of the shell program
		- `$#`  : number of arguments passed
		- `$1` or `${1}`  : first argument
		- `${11}`  : eleventh argument
		- `$*` or `$@`  : all arguments at once
		- `"$*"`  : all arguments as a single string
		- `"$@"`  : all arguments as separate strings
	- Command substitution
		- var=\`command\` OR `var=$(command)`
		- command is executed and the output is substituted
	- for do loop
		```bash
		for var in list
		do
			commands
		done
		```
		- commands are executed for each item in the list
		- set `IFS` if required, as a field separator
	- case statement
		```bash
		case var in
		pattern1)
			commands
			;;
		pattern2)
			commands
			;;
		esac
		```
		- commands are executed each pattern matched for var in the options
	- if loop
		```bash
		if condition
		then
			commands
		fi
		
		# OR
		
		if condition; then
			commands
		fi
		```
		- conditions used in the 'if' loop ![[Screenshot 2024-02-20 at 8.13.00 PM.png]]
	- Types of expressions in `if` conditions: ![[Screenshot 2024-02-20 at 8.23.16 PM.png]]![[Screenshot 2024-02-20 at 8.23.42 PM.png]]![[Screenshot 2024-02-20 at 8.23.59 PM.png]]![[Screenshot 2024-02-20 at 8.24.32 PM.png]]![[Screenshot 2024-02-20 at 8.25.06 PM.png]]
	- while do loop
		```bash
		while condition
		do
			commands
		done
		```
		- commands are executed only if condition returns true
	- until do loop
		```bash
		until condition
		do
			commands
		done
		```
		- commands are executed only condition returns false
	- functions
		```bash
		myfunc () 
		{
			commands
		}
		
		myfunc  # function call
		```
	- Code practice
		- when the script file was executed using `. <file.sh>`, it was run in the same shell but when it was executed using the relative path, `./<file.sh>`, bash had created a new child shell to execute the file.
			- any changes made in the child shell will not be available to the parent environment. variables will not be available
	- Debugging
		- `set -x` inside the script <u>OR</u> use `bash -x ./myscript.sh` when executing the script  : Prints the command before executing it
	- Combining conditions
		- `[ $a -gt 3 ] && [ $a -gt 7 ]`  : AND operator
		- `[ $a -gt 3 ] || [ $a -gt 7 ]`  : OR operator
	- Shell arithmetic ![[Screenshot 2024-02-21 at 8.50.44 PM.png]]
	- `expr` command operators![[Screenshot 2024-02-21 at 8.52.32 PM.png]]![[Screenshot 2024-02-21 at 8.53.06 PM.png]]
	- `heredoc` feature![[Screenshot 2024-02-21 at 9.10.07 PM.png]]
	- Code example: `IFS` sets the field separator as ":" so the $PATH variable becomes an array  ![[Screenshot 2024-02-21 at 9.16.42 PM.png]]
	- `if-elif-else-fi` loop ![[Screenshot 2024-02-21 at 9.19.32 PM.png]]
	- `case` statement![[Screenshot 2024-02-21 at 9.21.48 PM.png]]example script: ![[Screenshot 2024-02-21 at 9.22.58 PM.png]]
	- c style `for` loop : one variable![[Screenshot 2024-02-21 at 9.25.51 PM.png]]two variables: ![[Screenshot 2024-02-21 at 9.26.25 PM.png]]
	- processing output of a loop ![[Screenshot 2024-02-21 at 9.32.54 PM.png]]example code: ![[Screenshot 2024-02-21 at 9.34.54 PM.png]]
	- `break` out of a loop ![[Screenshot 2024-02-21 at 9.37.04 PM.png]]to break out of outer loops: ![[Screenshot 2024-02-21 at 9.38.37 PM.png]]
	- `continue` statement![[Screenshot 2024-02-21 at 9.41.43 PM.png]]
	- `shift` statement![[Screenshot 2024-02-21 at 9.43.36 PM.png]]example code: ![[Screenshot 2024-02-21 at 9.46.27 PM.png]]
	- `exec` command![[Screenshot 2024-02-21 at 9.47.37 PM.png]]
	- `eval` command![[Screenshot 2024-02-21 at 10.02.27 PM.png]]
	- `getopts` command ![[Screenshot 2024-02-21 at 10.09.06 PM.png]]example code:![[Screenshot 2024-02-22 at 6.40.17 PM.png]]
	- `select` loop![[Screenshot 2024-02-22 at 6.41.45 PM.png]]example code: ![[Screenshot 2024-02-22 at 6.44.20 PM.png]]

# <u>Week 6</u>
- Packages to install:
	- `clinfo, coreutils, dmidecode, fdisk, hardinfo, hdparm, hwinfo, lshw, memtester, net-tools, pciutils, procps, sysstat, upower, util-linux`
- #### Knowing Hardware
	- `hwinfo`  : hardware information; processors, devices plugged in, partitions in the system
	- `lshw`  : list hardware; limited information
		- `lshw -c display`  : will give information only for the display
	- `cat /proc/cpuinfo`  : info about the processors that are available
	- `cat /proc/partitions`  : various partitions created in the storage device
	- `lsblk -o NAME,SIZE`  : all the block devices with their names and storage sizes
	- `lspci`  : various pci devices connected to the computer
	- `sudo dmidecode --type memory`  : how is the memory installed; how many dim modules are used to have this RAM
	- `hardinfo`  : graphical way of looking at information
	- `clinfo`  : kind of graphics card; kind of libraries supported by the graphics card
	- `upower -e`  : names of all the battery devices
		- `upower -i <device_name>`  : info on the particular battery device
	- `sudo hdparm -Tt /dev/sda`  : hard disk parameter check on device called 'sda'. By sending and receiving data, it will tell you what's the speed it is operating at.
	- `ifconfig`  : info on network configuration

- #### Prompt String
	- <u>bash prompts</u>
		- PS1: primary prompt string: `$`
		- PS2: secondary prompt for multi-line input: `>`
		- PS3: prompt string in select loops: `#?`
		- PS4: prompt string for execution trace: `+`
		- Escape sequences![[Screenshot 2024-03-04 at 5.00.33 PM.png]]
	- Python command line
		- ps1 and ps2 are defined in the module 'sys'
		- Change sys.ps1 and sys.ps2 if needed
		- Override \_\_str__ method to have dynamic prompt
	- Code example:
		- `echo $PS1`  : gives details about PS1
			- `PS1="\u@\h:\w\$ "` will change the PS1 making it colorless
			- `PS1="\t:\w\$ "` will show current time in prompt string
			- `PS1="\d:\w\$ "` will show day and date 
			- `source .bashrc`  : will change it back to the default prompt string because the prompt is defined in `.bashrc`
		- `select x in alpha beta gamma; do echo $x; done`  : to try out PS3
		- After putting `set -x` and until putting `set -x` again, running every command will print the command being run in the format (`+<command>`)
- #### Important Utilities
	- `find`  : locating files and processing them
		- syntax : `find <pathnames> <conditions>`
		- conditions: ![[Screenshot 2024-03-04 at 5.51.02 PM.png]]
	- `tar, gzip`  : packaging collections of files
	- `make`  : conditional actions
	- ##### file packaging
		- Deep file hierarchies not recommended
		- Large number of tiny files, each occupying minimum block size so there's a wastage of space. `tar` fixes this
		- `tar`  : convert the entire file hierarchy into a single file and store it as a package
		- `gzip`  : compress a file
		- `Applications`  : backup, file sharing, reduce disc utilisation
		- `make`![[Screenshot 2024-03-04 at 6.23.22 PM.png]]
		- Code example:
			- `find $HOME -print`  : looks at the `$HOME` directory and print out the list of names of files present in the directory
			- `find $HOME -mtime -2 -print`  : files modified in the last 2 days printed out
			- `find . -mtime +30 -print`  : files in current directory that were last modified more than a month back
			- `find /usr -type d -name 'man*' -print`  : go to `/usr` and print out the directories that have the pattern `'man*` in their name
			- `find . -size +10M -print`  : files which are >10megabytes
				- `find . -size +10M -exec ls -lsh {}\;`  : all the files with size >10M will be placed in the `{}` brackets and the command `ls -lsh` will be executed
			- `find . -name '*.jpg' -exec ls -sh {} \;`  : Look for files in the current directory that end in 'jpg' and then execute `ls -sh` on those files
			- `tar -cvf logfiles.tar logfiles/`  : creating a bundle of all the files in the directory `logfiles/` and naming the bundle as logfiles.tar
				- `gzip logfiles.tar`  : compresses the file into a `.gz` format
					- `gunzip logfiles.tar.gz`  : to unzip
				- `bzip2 logfiles.tar`  : more efficient in shrinking but takes more time
					- `bzip2 -d logfiles.tar.bz2`  : to unzip
				- `compress logfiles.tar`  : very fast but doesn't shrink so much
					- `uncompress logfiles.tar.Z`  : to unzip
				- `tar -xvf logfiles.tar`  : to untar the file and create a directory out of it
			- create file `make.file` with the following text in it: ![[Screenshot 2024-03-04 at 7.47.43 PM.png]]then run `make -f make.file backup`. This will run  the backup command from the file 

- #### Automating Scripts
	- <u>cron</u> service
		- to run scripts automatically at schedules times
		- Tools: `at`, `crontab`, `anacron`, `logrotate`
		- Script locations: `/etc/crontab`, `/etc/cron.d`, `/etc/cron.hourly`, `/etc/cron.daily`, `/etc/cron.weekly`, `/etc/cron.monthly`
	- Job definition in cron ![[Screenshot 2024-03-04 at 10.24.09 PM.png]]
	- Startup scripts
		- `/etc/init/`, `/etc/init.d/`
		- Runlevel scripts: different modes Linux system can be run on ![[Screenshot 2024-03-04 at 10.27.11 PM.png]]
	- code example:
		- mkbackup.sh:
			```bash
			BFILE=/home/akulbansal/Desktop/backup/mkbackup.log
			echo "starting backup automatically" >> $BFILE
			date >> $BFILE
			echo "backup process completed" >> $BFILE
			echo "-----------------------------" >> $BFILE
			```
		- `crontab -e` will open the editor

- #### sed
	- programming language for processing strings
	- abbreviation for <u>s</u>tream <u>ed</u>itor
	- ##### Execution model
		- input stream: set of lines
		- data buffers maintained: active <u>pattern</u> space and auxiliary <u>hold</u> space
		- script will contain a set of commands and each execution cycle is performed on every loading line
	- usage:
		- Single line at command line: `sed -e 's/hello/world/g' input.txt`
		- myscript.sed:
			```sed
			#!/usr/bin/sed -f
			2,8s/hello/word/g
			```
		- Script interpreted by sed: `sed -f ./myscript.sed input.txt`
	- sed statements![[Screenshot 2024-03-05 at 7.01.47 PM.png]]
	- `{ cmd; cmd }`  : grouping commands
	- address![[Screenshot 2024-03-05 at 7.02.54 PM.png]]
		- `5`  : 5th line alone will be chosen
		- `$`  : last line
		- `%`  : all the lines
		- `1~3`  : every third line starting from the first line will be processed
	- actions (single-letter commands)![[Screenshot 2024-03-06 at 12.05.28 PM.png]]
	- programming![[Screenshot 2024-03-06 at 12.06.14 PM.png]]
	- use sed to pre-process input for further processing by other scripts
	- ###### Code example
		- sample.txt : ![[Screenshot 2024-03-06 at 12.28.08 PM.png]]
		- `sed -e "" sample.txt`  : prints all the lines
		- `sed -n -e "" sample.txt`  : default action of printing is suppressed
		- `sed -e "=" sample.txt`  : prints the line number for each line
		- `sed -n -e "5p" sample.txt`  : print the 5th line and suppress rest of the lines
		- `sed -n -e '5!p' sample.txt`  : print every line except the 5th line
		- `sed -n -e '5,8{=;p}' sample.txt`  : line number and line itself from 5th to 8th line
		- `sed -n -e '1~2p' sample.txt`  : starting line, every second line after that (prints odd line)
		- `sed -n -e '/microsoft/p' sample.txt`  : print every line that contains that particular word
		- `sed -n -e '/adobe/,+2p' sample.txt`  : print two lines after the matching
		- `sed -e '5d' sample.txt`  : delete 5th line
		- `sed -e '5,8d' sample.txt`  : delete 5th to 8th lines
		- `sed -e '/microsoft/d' sample.txt`  : delete all the lines containing 'microsoft'
		- `sed -e 's/microsoft/MICROSOFT/g' sample.txt`  : replace 'microsoft' with 'MICROSOFT'
		- `sed -e '1s/linux/LINUX/g' sample.txt`  : substitution only on the first line
		- `sed -E -e '3,6s/^L[[:digit:]]+ //g' sample.txt`  : remove the numbers from the beginning of the line, only for 3rd to 6th line
		- `sed -E -e '3,/symbolic/s/^L[[:digit:]]+ //g' sample.txt`  : same as previous command but apply only to 3rd line until the line in which 'symbolic' word is present
		- `sed -E -e '/text/,/video/s/^L[[:digit:]]+ //g' sample.txt`  : from the line that contains the word 'text' to the line that contains the word 'video', remove the "L<\number>"
		- `sed -e '1i ----------header----------' sample.txt`  : <u>inserts</u> the text in quotes at the 1st line
		- `sed -e '1i ----------header----------' -e '$a ----------footer----------' sample.txt`  : <u>inserts</u> before the 1st line and <u>appends</u> after the last line
		- `sed -e '1~5i ----------break----------' sample.txt`  : inserts the text before every 5th line, starting from the 1st line
		- `sed -e '/microsoft/c ----------censored----------' sample.txt`  : every line that has 'microsoft', change the line ('c' command) with the text that has been given
		- `sed -e '1~3c ----------censored----------' sample.txt`  : 1st line onwards, every 3rd line is 'censored'
		- hf.sed (sed script)
			```sed
			#!/usr/bin/sed -f
			1i ---------- header ----------
			$a ---------- footer ----------
			1,5s/in place of/in lieu of/g
			6i 1i ---------- simpler stuff here onward ----------
			6,$s/in place of.*//g
			```
			- `sed -f hf.sed sample.txt`  : above-mentioned 5 different commands can executed on `sample.txt` at the same time by running the command
		- sed script example:![[Screenshot 2024-03-06 at 5.32.04 PM.png]]
			- `s/ ([[:digit:]]+).*/ \1/g`  : anything after which the number has come, then only the number has to be kept and remaining space could be replaced
		- sample-split.txt : ![[Screenshot 2024-03-06 at 5.42.03 PM.png]]same as sample.txt except some lines are ending with `\` and we want to join those lines with the following line. need to run a loop for this.
			- sed script for this:
				```sed
				#!/usr/bin/sed -f
				:x /\\$/N
				/\\/s/\\\n//g
				/\\$/bx
				```
				- <u>first line</u>: whenever there's a `\` followed by the end of the line, then it will read the next line into the buffer
				- <u>second line</u>: on the lines which has `\`, if there's a character `\n` after the `\` replace it with null
				- <u>third line</u>: on those lines, which contain `\` at the end of the line, we branch the first line

# <u>Week 7</u>
- #### awk
	- programming language
	- Eg., using '\\n' as record separator, lines are records
	- Each record is a sequence of fields
	- Eg., using " " as field separators, words are fields
	- Each code block executes on one record at a time, as matched by the pattern of that block
	- usage
		- `cat /etc/passwd | awk -F":" '{print $1}'`
	- Built-in variables![[Screenshot 2024-03-11 at 4.08.43 PM.png]]![[Screenshot 2024-03-11 at 4.09.46 PM.png]]
	- awk scripts![[Screenshot 2024-03-11 at 4.10.36 PM.png]]
	- execution![[Screenshot 2024-03-11 at 4.11.41 PM.png]]
	- Operators![[Screenshot 2024-03-11 at 4.12.32 PM.png]]![[Screenshot 2024-03-11 at 4.13.00 PM.png]]
	- Functions and commands![[Screenshot 2024-03-11 at 4.13.56 PM.png]]
	- arrays
		- associative arrays; sparse storage; index need not be integer
		- `arr[index]=value` ; `for (var in arr)` ; `delete arr[index]`
	- loops![[Screenshot 2024-03-11 at 4.56.51 PM.png]]
	- functions: `cat infile | awk -f mylib -f myscript.awk`![[Screenshot 2024-03-11 at 5.10.47 PM.png]]
	- pretty printing![[Screenshot 2024-03-11 at 5.18.33 PM.png]]
	- `dig -x <IP_address>` to know more about the IP address
	- code example
		- block-ex-1.awk file:
			```bash
			#!/usr/bin/gawk -f
			BEGIN{
				print "BEGIN action is processed";
			}
			{
				print "Default action is processed";
			}
			END{
				print "END action is processed";
			}
			```
		- block-ex-1.input file:
			```bash
			line-1 word1a word1b word1c
			line-2 word2a word2b word2c
			line-3 word3a word3b word3c
			```
		- `./block-ex-1.awk block-ex-1.input`  ![[Screenshot 2024-03-11 at 4.02.40 PM.png]]for each line in the input file, the middle block is being processed
		- example of using built-in variables ![[Screenshot 2024-03-11 at 4.15.33 PM.png]]
		- regular expression on action blocks ![[Screenshot 2024-03-11 at 4.25.25 PM.png]]the blocks will only be executed on the lines where the respective regex matches
		- only the first field will be matched with regex instead of matching the entire record ![[Screenshot 2024-03-11 at 4.28.18 PM.png]]
		- looks at the number of fields to filter which record to run the process on; Field Separator is in the `BEGIN` block (' ' or '.' or ',' or ':' or '-') ![[Screenshot 2024-03-11 at 4.30.34 PM.png]]
		- example script to get the roll numbers and fees paid by each roll number ![[Screenshot 2024-03-11 at 5.01.02 PM.png]]input:![[Screenshot 2024-03-11 at 5.02.50 PM.png]]output:![[Screenshot 2024-03-11 at 5.03.11 PM.png]]
		- creates 2 millions rows and 2 columns of random numbers ![[Screenshot 2024-03-11 at 5.21.18 PM.png]]created 2 million lines in a very short time ![[Screenshot 2024-03-11 at 5.23.49 PM.png]]
		- processed 2 million records (which were generated in the last code example) in 4.5 seconds! ![[Screenshot 2024-03-12 at 2.37.27 PM.png]]
		- print the first field of every record in the file `access-head.log` ![[Screenshot 2024-03-12 at 2.54.59 PM.png]]
		- printing only the dates from the log file ![[Screenshot 2024-03-12 at 2.56.48 PM.png]]
		- Looking at which IP addresses accessed the server in the last `n` days from the log file
			```bash
			#!/usr/bin/gawk -f
			BEGIN{
				ndays=5
				dformat="+%d/%b/%Y"
				for (i=0; i<ndays; i++) {
					cmdstr=sprintf("date --date=\"%d days ago\" %s", i, dformat)
					cmdstr | getline mydate
					dates[i]=mydate
				}
				dstring = ""
				for (i in dates) {
					dstring = dstring " " dates[i]
				}
				print "date sring=" dstring
			}
			{
				ldate=substr($4,2,11) # 4th field, from 2nd char to 11th char
				w = match(dstring,ldate)
				if(w!=0) {
					# print ldate " " $1 " " $7
					print ldate " " $1
					ipcount[$1]++
				}
			}
			END{
				print "ip stats---------------------------------"
				for (j in ipcount) {
					print j " " ipcount[j]
				}
			}
			```

# <u>Week 8</u>
- Three types of addresses: ![[Screenshot 2024-03-25 at 3.10.45 PM.png]]
	- Localhost: so the system can refer to itself
	- Private network
		- Class A: meant for large organisation; 16 millions IPs possible
		- Class B: 1 million IPs possible
		- Class C: 65 thousand IPs possible
		- there cannot be any publicly visible addresses with these IP addresses
	- Public network: all the other addresses
- There can be private network within a private network, by having multiple layers of routing; only possible up to three layers because only three types of private network available
- ##### Ports
	- each port number is meant for a particular service
	- VPN access; ssh tunneling; remote desktop; desktop over browser; commercial, over internet (Teamviewer, AnyDesk)
	- Some important ports ![[Screenshot 2024-03-25 at 3.29.14 PM.png]]
- ##### Firewall
	- Ports needed to be accessed on remote machine
	- Network routing over the port
	- Firewall controls at each hop
- SELinux
	- Security Enhanced Linux mode
	- Additional layer of access control on files to services
	- Role based Access Control
	- Process sandboxing, least privilege access for subjects
	- Check using `ls -lZ` and `ps -eZ`
- Network tools![[Screenshot 2024-03-25 at 3.58.36 PM.png]]
- `dig google.com`  : will get the IP address of a particular machine

- ### Managing Storage
	- LVM
		- Logical Volume Management
		- Pooling multiple storage devices as a single logical volume
		- lvm2 tools: create and manage virtual block devices from physical devices
	- RAID
		- Redundant Arrays of Independent Disks
		- Distributing over multiple discs for redundancy/speed/increased capacity
		- RAID modes ![[Screenshot 2024-03-25 at 4.22.40 PM.png]]
	- 