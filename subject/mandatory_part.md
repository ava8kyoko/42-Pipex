# Mandatory part

|                                  |                                                    |
| -------------------------------- | -------------------------------------------------- |
| **Program name**                 | pipex
| **Files**                        | Makefile, \*.h, \*.c 
| **Makefile**                     | NAME, all, clean, fclean, re
| **Arguments**                    | file1 cmd1 cmd2 file2
| **External fonctions autorised** | • open, close, read, write, malloc, free, perror, <br>                                                                                strerror, access, dup, dup2, execve, exit, fork, <br>                                                                                pipe, unlink, wait, waitpid <br>                                                                                                  • ft_printf nd any equivalent YOU coded
| **Libft autorised**              | Yes
| **Description**                  | This project is about handling pipes


## Makefile

|                                  |                                                        |
| -------------------------------- | ------------------------------------------------------ |
| **NAME**                         | Path of every source files
| **all**                          | Compile \*.c, i.e. every source code files
| **clean**                        | Delete every \*.o, i.e. every object files 
| **fclean**                       | Same as clean, but delete a.out, i.e. executable, too
| **re**                           | 


## Arguments

It must take 4 arguments:
- file1 and file2 are file names.
- cmd1 and cmd2 are shell commands with their parameters.

### Programme execution
`./pipex file1 cmd1 cmd2 file2` <br>
<br>
Votre programme doit se comporter exactement comme la commande shell suivante : <br>
`$> < file1 cmd1 | cmd2 > file2`

#### Examples
`$> ./pipex infile "ls -l" "wc -l" outfile` <br>
Devrait être identique à < infile ls -l | wc -l > outfile <br>
<br>
`$> ./pipex infile "grep a1" "wc -w" outfile` <br>
Devrait être identique à < infile grep a1 | wc -w > outfile
