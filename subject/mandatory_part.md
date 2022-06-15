# Mandatory part

|                                  |                                                           |
| -------------------------------- | --------------------------------------------------------- |
| **Program name**                 | pipex
| **Files**                        | Makefile, \*.h, \*.c 
| **Makefile**                     | NAME, all, clean, fclean, re
| **Arguments**                    | file1 cmd1 cmd2 file2
| **External fonctions autorised** | • open, close, read, write, malloc, free, perror, <br>                                                                                                        strerror, access, dup, dup2, execve, exit, fork, <br>                                                                                                      pipe, unlink, wait, waitpid <br>                                                                                                                          • ft_printf or any equivalent YOU coded
| **Libft autorised**              | Yes
| **Description**                  | This project is about handling pipes


## Makefile

| Mandatory                        |                                                        |
| -------------------------------- | ------------------------------------------------------ |
| **NAME**                         | Path of every source files
| **all**                          | Compile \*.c, i.e. every source code files
| **clean**                        | Delete every \*.o, i.e. every object files 
| **fclean**                       | Same as clean, but delete a.out, i.e. executable, too
| **re**                           | fclean + all


| My own rules                     |                                                        |
| -------------------------------- | ------------------------------------------------------ |
| **leaks**                        |
| **test**                         | 
|                                  |


## Arguments

It must take 4 arguments:
- file1 and file2 are file names.
- cmd1 and cmd2 are shell commands with their parameters.

#### What is an argument ?

Arguments are parameters/arguments supplied to the program when it is invoked. They are used to control program from outside instead of hard coding those values inside the code. They are passed to main() function. 

- `int main(int argc, char **argv) { /* ... */ }`
- argc (ARGument Count) is int and stores number of argument + the name (name = 1, arguments >= 2). Should be non negative.
- argv (ARGument Vector) is array of character pointers listing all the arguments.
- If argc > 0, the array elements from argv[0] to argv[argc-1] (because ) will contain pointers to strings.
- argv[0] holds the name of the program
- argv[1] points to the first command line argument and argv[argc-1] points last argument.
- argv[argc] is a NULL pointer.

Note : You pass all the command line arguments separated by a space, but if argument itself has a space then you can pass such arguments by putting them inside double quotes `" "` or single quotes `' '`.

#### What is a shell command ?

A shell is a computer program that presents a command line interface which allows you to control your computer using commands entered with a keyboard instead of controlling graphical user interfaces (GUIs) with a mouse/keyboard/touchscreen combination.

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

## External fonctions autorised

|             |                                |                                |                                           |     |
| ----------- | ------------------------------ | ------------------------------ | ----------------------------------------- | --- |
| open()      | open and possibly create a file | fcntl.h |  | [x](https://man7.org/linux/man-pages/man2/open.2.html)
| close()     | close a file descriptor | unistd.h | int close(int fd); | [x](https://man7.org/linux/man-pages/man2/close.2.html)
| read()      | read from a file descriptor | unistd.h | ssize_t read(int fd, void \*buf, size_t count); | [x](https://man7.org/linux/man-pages/man2/read.2.html)
| write()     | write to a file descriptor | unistd.h | ssize_t write(int fd, const void \*buf, size_t count); | [x](https://man7.org/linux/man-pages/man2/write.2.html)
| malloc()    | allocate dynamic memory | stdlib.h | void \*malloc(size_t size); | [x](https://man7.org/linux/man-pages/man3/malloc.3.html)
| free()      | free dynamic memory | stdlib.h | void free(void \*ptr); | [x](https://man7.org/linux/man-pages/man3/malloc.3.html)
| perror()    | print a system error message | stdio.h | void perror(const char \*s); | [x](https://man7.org/linux/man-pages/man3/perror.3.html)
| strerror()  | return string describing error number | string.h || [x](https://man7.org/linux/man-pages/man3/strerror.3.html)
| access()    | check user's permissions for a file |  |  | [x](https://man7.org/linux/man-pages/man2/access.2.html)
| dup()       | duplicate a file descriptor | unistd.h | int dup(int oldfd); | [x](https://man7.org/linux/man-pages/man2/dup.2.html)
| dup2()      | duplicate a file descriptor | unistd.h | int dup2(int oldfd, int newfd); | [x](https://man7.org/linux/man-pages/man2/dup.2.html)
| execve()    | 
| exit()      |
| fork()      |
| pipe()      |
| unlink()    |
| wait()      |
| waitpid()   |
| ft_printf() |


## References

- [Command line arguments](https://www.geeksforgeeks.org/command-line-arguments-in-c-cpp/)
- [Introduction to command shell](https://datacarpentry.org/shell-genomics/01-introduction/)

### Not used

- [Communication par tuyau](http://www.zeitoun.net/articles/communication-par-tuyau/start)
- [Implementation of pipe in linux](https://www.slideshare.net/tusharkute/implementation-of-pipe-in-linux?next_slideshow=1)
- [Pipes, Forks, & Dups: Understanding Command Execution and Input/Output Data Flow](https://www.rozmichelle.com/pipes-forks-dups/)
- [Piping in Unix or Linux](https://www.geeksforgeeks.org/piping-in-unix-or-linux/)
- [Pipes and File I/O](https://slideplayer.com/slide/11637035/)
- [Programmation systeme: execve() fork() et pipe()](https://n-pn.fr/t/2318-c--programmation-systeme-execve-fork-et-pipe)
- [Redirection](https://datacarpentry.org/shell-genomics/04-redirection/index.html)
- Forum [fork after malloc in parent... does the child process need to free it?](https://stackoverflow.com/questions/23440132/fork-after-malloc-in-parent-does-the-child-process-need-to-free-it#:~:text=You%20do%20not%20need%20to,bright%20idea%20to%20do%20so.&text=You%20seem%20to%20be%20basically,not%20worry%20about%20freeing%20stuff)
- Forum [Redirection exec output to a buffer or file](https://stackoverflow.com/questions/2605130/redirecting-exec-output-to-a-buffer-or-file)
- Forum [Unix pipe into ls](https://stackoverflow.com/questions/18210956/unix-pipe-into-ls)
- Forum [Write on pire in c](https://stackoverflow.com/questions/47503798/write-on-pipe-in-c)
- Code [redir_handler](https://github.com/Kampouse/mini-shell-racoon/blob/jp_v2/executing/redir_handler.c)
- Code [redir](http://gunpowder.cs.loyola.edu/~jglenn/702/S2005/Examples/dup2.html)
- Tutorial [pipex 42](https://csnotes.medium.com/pipex-tutorial-42-project-4469f5dd5901)
- Videos [Unix process in C](https://www.youtube.com/playlist?list=PLfqABt5AS4FkW5mOn2Tn9ZZLLDwA3kZUY)
- Video [Tubes anonymes et nommes](https://www.youtube.com/watch?v=k8bGYB2gl-A&t=824s)
- [Tester](https://github.com/vfurmane/pipex-tester)
