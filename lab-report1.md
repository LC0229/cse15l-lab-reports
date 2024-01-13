# `cd`

## `cd` with no arguments
`[user@sahara ~]$ cd` </br>
`[user@sahara ~]$`

*working directory*</br>
`[user@sahara ~]$ pwd`</br>
`/home`

For this case, the result is that nothing happend in this case. Since if there is no argument for cd, the system have no change to working directory. The current working directory is still `/home`.

The output is not an error.


## `cd` with a path to a directory as an argument.
`[user@sahara ~]$ cd lecture1/`</br>
`[user@sahara ~/lecture1]$ `

*working directory*</br>
`[user@sahara ~/lecture1]$ pwd` </br>
`/home/lecture1`

For this case, the result is that we are going to a new Working directory called lecture1, since after we put the path after cd, we swtich current working directory `/home` to given new directory `/home/lecture1`.
The output is not an error.


## `cd` with a path to a file as an argument.
`[user@sahara ~/lecture1]$ cd README`</br>
`bash: cd: README: Not a directory`

*working directory*</br>
'[user@sahara ~/lecture1]$ pwd` </br>
`/home/lecture1`

For this case, the result indicates an error for Not a directory, since cd does not take file as an argument, it is designed to change the current working directory.



# `ls`

## `ls` with no arguments
`[user@sahara ~]$ ls`</br>
`lecture1`

*working directory*</br>
`[user@sahara ~]$ pwd`</br>
`/home`

For this case, after we implements ls, it tells us the folder called lecture1 is in the home working directory. The current working directory is still `/home`.
The output is not an error.


## `ls` with a path to a directory as an argument.
`[user@sahara ~]$ ls lecture1/`</br>
`Hello.class  Hello.java  messages  README`

*working directory*</br>
`[user@sahara ~]$ pwd`</br>
`/home`

For this case, after we put ls with directory, it gives us files and folders in the directory. The current working directory is still `/home`, which remains unchanged.
The output is not an error.


## `ls` with a path to a file as an argument.
`[user@sahara ~/lecture1]$ cd README`</br>
`bash: cd: README: Not a directory`

*working directory*</br>
'[user@sahara ~/lecture1]$ pwd` </br>
`/home/lecture1`

For this case, the result indicates an error for Not a directory, since cd does not take file as an argument, it is designed to change the current working directory.
The output is not an error.


# `cat`

## `cat` with no arguments
`[user@sahara ~]$ cat`</br>
`Hello World!`(input)</br>
`Hello World!`(output)

*working directory*</br>
`[user@sahara ~]$ pwd`</br>
`/home`

For this case, the result displays the content of my standard input. There is no change for working directory.
The output is not an error.




## `cat` with a path to a directory as an argument.
`[user@sahara ~]$ cat lecture1`</br>
`cat: lecture1: Is a directory`

*working directory*</br>
`[user@sahara ~]$ pwd`</br>
`/home`

For this case, te result displays an error, the directory i input is not valid as an argument of cat. Since cat is used to display the content of files.




