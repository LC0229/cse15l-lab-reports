# `cd`

## `cd` with no arguments
`[user@sahara ~]$ cd` </br>
`[user@sahara ~]$`

*working directory*
`[user@sahara ~]$ pwd`</br>
`/home`

For this case, the result is that nothing happend in this case. Since if there is no argument for cd, the system have no change to working directoyr. The current working directory is still `/home`.

The output is not an error.


## `cd` with a path to a directory as an argument.
`[user@sahara ~]$ cd lecture1/`</br>
`[user@sahara ~/lecture1]$ `

*working directory*
`[user@sahara ~/lecture1]$ pwd` </br>
`/home/lecture1`

For this case, the result is that we are going to a new Working directory called lecture1, since after we put the path after cd, we swtich current working directory `/home` to given new directory `/home/lecture1`.
The output is not an error.


## `cd` with a path to a file as an argument.
`[user@sahara ~/lecture1]$ cd README`</br>
`bash: cd: README: Not a directory`

*working directory*
'[user@sahara ~/lecture1]$ pwd` </br>
`/home/lecture1`

For this case, the result indicates an error for Not a directory, 
