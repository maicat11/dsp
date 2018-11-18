# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> > **BASH in terminal/command line**  
>> _`[command] [options] [arguments]`_  

>> **`clear`**				(clear the screen) 
>> **`touch`** 				(create or modify a file without open, save, close)  
>> **`echo`** "text"			(print text)  
>> **`echo`** "text">>file 		(add text to a file  one > will overwrite the file)  
>> **`echo`** $'single\nquotes' > file	(needed for entering special characters in text such as a new line...will print single    quotes on separate lines)  
>> **`nano`** file 			(modify with in a file, ctrl+x to quit, y enter to save)  
>> **`cd`**				(change directory to ...)  
>> **`cd ~`**				(change directory back to home/root)  
>> **`cd ..`**				(change out of current directory "up" a folder)  
>> **`ls`**				(list)  
>> **`ls -l`**				(list with flag to show details of files)  
>> **`ls`** folderName			(list only files in this folder)  
>> **`-v`**				(verbose mode, for print output when folder created)  
>> **`-a`** 				(ls -a will show everything in a folder even if it starts with a .)  
>> **`mv`** file to file			(move or rename a file)  
>> **`pwd`**				(print working directory or "path" currently in)  
>> **`chmod`** #### file			(change users abilities to read, write, execute)  
>> **`cp`** file to 			(copy)  
>> **`rm`** file				(remove file)  
>> **`sudo`** 				(change to root user, need password)  
>> **`whoami`**				(check user)  
>> **`--help`**				(use with any command to get info about it)  
>> **`grep`** 				(search through the contents of a set of files to find a specific line of text.)  
>> **`name?.file_ext`**			(the ? is a wild card to search multiple files that start with the same name)  
>> **`*.file_ext`**			(the * is a wild card that searches in multiple files that end in the same file                extension)  
>> **`command | command`**		(allows you to send output from one command to input of another command. Useful for chaining commands together.)  
>> **`command && command`** 		(run two commands sequentially, but not pass output between them)  
>> **`cat`** filename 			(print the contents of a file)  
>> **`cat`** filename1 filename2		(concatenate - print both files in that order)  
>> **`less`** folderName/filename	(use if printing a large file to be able to scroll page by page)  
>> **`head`** folderName/filename	(use if printing a large file just to see the first few lines)  
>> **`head`** -n value (i.e. 4)		(specific number of lines (i.e. 4) from head...can also be used in tail command)  
>> **`tail`** folderName/filename	(use if printing a large file just to see the last few lines)  
>> **`tail`** -n value  file>>file  	(append rows from one file into another)  
>> **`head`** -1 file>file		(flag to append header row to a file)  
>> **`wc`** folderName/filename		(gives -> lineCount, wordCount, characterCount)  
>> **`wc`** -l file			(indicates the the length of the dataframe)  
>> **`nano`** fileName			(takes to a more text editor friendly page where more content can be added or altered)  

_Moving, renaming, copying, and deleting files and folders_

>> **`mkdir`** folderName		(make a new folder in the current directory)  
>> **`rmdir`** folderName		(delete folder in the current directory)  
>> **`mv`** fileName folderName		(move file from current directory to another folder.  You can also move a folder to a folder.)  
>> **`cp`** fileName folderName		(copy file from current directory to another folder.)  
>> **`cp -r`** folderName folderName	(copy folder from current directory to another folder. The -r is necessary for folder copying to maintain integrity)  
>> **`rm`** fileName			(remove or delete file from current directory)  
>> **`rm -r`** folderName/folderName	(remove folder from directory, the -r is needed) . 

>> **`man ls`** 				(Use when searching for an unknown or forgotten command.  Type "/" and the word need to search to find the commend needed.)  
				(press "n" to find next occurance of the word or "shift n" to find previous occurance of the word.)  
>> **`apropos`** (word to search)	(lists all avaiable "words" associated with your word.  More verbose search.)  


>> **`---`**			(No permissions)  
>> **`--x`**			(execute only)  
>> **`-w-`**			(write only)  
>> **`-wx`**			(write and execute)  
>> **`r--`**			(read only)  
>> **`r-x`**			(read and execute)  
>> **`rw-`**			(read and write)  
>> **`rwx `**			(read, write, and execute)  

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

> > **`ls`** -> List all directories and files in current path  
>> **`ls -a`** -> List all directories and files in current path including hidden ones  
>> **`ls -l`** -> List long format, displaying Unix file types, permissions, number of hard links, owner, group, size, last-modified date and filename  
>> **`ls -lh`** -> List long format (same as above) with readable file size  
>> **`ls -lah`** ->  List long format (same as above) with readable file size and hidden files  
>> **`ls -t`** -> List all directories sorted by date and time  
>> **`ls -Glp`** -> List long format, color coordinating the file/directory name  
---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

>> **Five favorites**  
>> **`ls -r`** -> Displays files in reverse order  
>> **`ls -R`** -> Displays subdirectories as well  
>> **`ls -u`** -> Displays files by the file access time  
>> **`ls -F`** -> Flags filenames  
>> **`ls -m`** -> Displays the names as a comma-separated list  


---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

>> **`xargs`** is a command on Unix operating systems used to build and execute commands from standard input. It converts input from standard input into arguments to a command.  

>> For example, 
>> >> _`printf "one\ntwo\nthree\n" | xargs mkdir`_  

>> will simultaneously create 3 folders "one", "two", "three" 
 

