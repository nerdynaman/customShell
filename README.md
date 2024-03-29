# Custom Shell
Tried to recreate a shell in C. It is not a fully functional shell, but it can run some commands.

#### External commands
    
`cat` `date` `ls` `mkdir` `rm`

above mentioned commands have been implemented using `fork` and `thread` system calls.

#### Internal commands

`cd` `echo` `pwd`

## Installation

Type following in main project directory 

    make
    ./main

## Usage

#### Assumption
Any file name doesn't contains a space
doing a blank enter and writing exit on the shell will exit the shell

#### cat
flags implemented : `n` and `e`

1) Both flags can be used together and are optional
2) It will give error if no parameters are passed
3) It will give error if wrong path is entered
4) It will give error if a directory is entered
5) If one path is wrong then entire statement will not be stopped
6) It will check for correct flag

        usage : cat [-flag] [file ...]

        -n : number all output lines

        -e : display $ at the end of each line

        ex: cat -ne file1 file2 || cat -n file1 file2 || cat -e file1 file2 || cat file1 file2

#### date
flags implemented : `u` and `r`

1)Both flags can be used together and are optional

2)It will give error if wrong path is enterred

3)It will check if proper syntax is used and arguments are passed

4)It will check for correct flag

    usage : date [-u] [-r file] 

    -u : print or set Coordinated Universal Time (UTC)

    -r : display the last modification time of file or directory

    ex: date -ur file1 || date -r file1 || date -u || date
#### ls
flags implemented : `a` and `d`

1)both flags can be used together and are optional

2)it will give error if wrong path is enterred

3)it will give error if file is enterred

4)it will check for correct flag

    usage : ls [-a|d] [file ...]

    -a : do not ignore entries starting with `.`

    -d : list directory entries instead of contents

    ex: ls -ad [file1 ...] || ls -d [file1 ...]|| ls -a [file1 ...] || ls [file1 ...]

#### mkdir
flags implemented : `v` and `m`
1) Both flags can be used together and are optional

2) It will give error if directory exists

3) It will give error for wrong mode enterred

4) It will give error if wrong path is enterred

5) It will give error if file is enterred

6) It will check for correct flag



        usage : mkdir [-v] [-m mode] [file ...]

        -v : print a message for each created directory

        -m : set file mode (as in chmod)

        ex: mkdir -vm [file1 ...] || mkdir -v [file1 ...] || mkdir -m 0751 [file1 ...] || mkdir [file1 ...]


```mode is an octal number where each digit represents the permissions for the owner, group and others and the first digit has to be 0 and other subsequent digits can be sum of 1,2,4 (1 for execute, 2 for write and 4 for read)```

#### rm
flags implemented : `d` and `v`

1) Both flags can be used together and are optional

2) It will give error if wrong path is enterred

3) It will give error if file is enterred

4) It will give error if trying to delete a directory without -d flag

5) It will give error of trying to delete non empty directory

6) It will check for correct flag

        usage : rm [-d] [-v] [file ...]

        -d : remove empty directories

        -v : explain what is being done

        ex: rm -vd [file1 ...] || rm -v [file1 ...] || rm -d [file1 ...] || rm [file1 ...]
#### pwd
flags implemented : none

It will give error if more than one argument is passed

It will print the current working directory

    usage : pwd

    ex: pwd

#### cd
flags implemented : no flags available

1) only cd and cd ~ also works

2) It will give error if more than one argument is passed

3) It will give error if wrong path is enterred

4) It will change the current working directory

    usage : cd [directory]

    ex: cd [path] || cd ~ || cd
#### echo
flags implemented : `n` and `help`
1) Both flags can not be used together and are optional
2) It will give error if wrong flag is enterred
3) It will work if no arguments are passed and print empty line

    usage : echo [-n | -help] [string ...]


    -n : do not output the trailing newline

    -help : display help
    
    ex: echo -n [string ...] || echo -help || echo [string ...]