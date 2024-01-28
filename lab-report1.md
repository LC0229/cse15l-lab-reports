# `cd`

## `cd` with no arguments

case1: current directory: /home

`[user@sahara ~]$ cd`

`[user@sahara ~]$`

case2: current directory: /lecture1

`[user@sahara ~/lecture1]$ cd`

`[user@sahara ~]$`

case3: current directory: /lecture1/messages

`[user@sahara ~/lecture1/messages]$ cd `

`[user@sahara ~]$`


For case1, the result is that nothing happend in case. For The current working directory is still `/home`. For case2, we can se the cd command lead us return to /home. For case3, if the current directory is /lecture1/messages, current directory returns to /home. 

The output is not an error for these cases.


## `cd` with a path to a directory as an argument.

current directory: /home

`[user@sahara ~]$ cd lecture1/`

`[user@sahara ~/lecture1]$ `

For this case, the result is that we are going to a new Working directory called lecture1, since after we put the path after cd, we swtich current working directory `/home` to given new directory `/home/lecture1`.
The output is not an error.


## `cd` with a path to a file as an argument.

current directory: /home/lecture1

`[user@sahara ~/lecture1]$ cd README`

`bash: cd: README: Not a directory`


For this case, the result indicates an error for Not a directory, since cd does not take file as an argument, it is designed to change the current working directory.



# `ls`

## `ls` with no arguments

current directory: /home

`[user@sahara ~]$ ls`

`lecture1`


For this case, after we implements ls, it tells us the folder called lecture1 is in the home working directory. The current working directory is still `/home`.
The output is not an error.


## `ls` with a path to a directory as an argument.

current directory: /home

`[user@sahara ~]$ ls lecture1/`

`Hello.class  Hello.java  messages  README`



For this case, after we put ls with directory, it gives us files and folders in the directory. The current working directory is still `/home`, which remains unchanged.
The output is not an error.


## `ls` with a path to a file as an argument.

current directory: /home/lecture1

`[user@sahara ~/lecture1]$ cd README`

`bash: cd: README: Not a directory`



For this case, the result indicates an error for Not a directory, since cd does not take file as an argument, it is designed to change the current working directory.
The output is not an error.


# `cat`

## `cat` with no arguments

current directory: /home

`[user@sahara ~]$ cat`

`Hello World!`(input)

`Hello World!`(output)



For this case, the result displays the content of my standard input. There is no change for working directory.
The output is not an error.




## `cat` with a path to a directory as an argument.

current directory: /home

`[user@sahara ~]$ cat lecture1`

`cat: lecture1: Is a directory`



For this case, te result displays an error, the directory i input is not valid as an argument of cat. Since cat is used to display the content of files.


## `cat` with a path to a file as an argument.

current directory: /home/lecture1

`[user@sahara ~/lecture1]$ cat messages/zh-cn.txt`

`你好世界`



For this case, the result displays the content of the file we put as arugment, the content of zh-cn.txt will be printed out. 
The output is not an error.



