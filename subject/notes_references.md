Note: It helps me to read a resume in french before english just to be sure to understand well.

### Communication par tuyau [:link:](http://www.zeitoun.net/articles/communication-par-tuyau/start)
Les pipes `|` permettent de faire communiquer les processus entre eux, i.e. rediriger la sortie d'une commande vers l'entrée d'une autre. ex: `ls | wc` EXPLIQUER LE PROCESSUS DANS MES MOTS <br>
<br>
<dl>
	<dt>Caracteristiques d'un pipe</dt>
		Possède deux extrémités.
		Les informations passent dans un sens unique
</dl>

Code : Création d'un pipe dans un processus unique <br>
```c
  #include <stdio.h>
  #include <memory.h>
  #include <unistd.h>
 
  int main( int argc, char ** argv )
  {
   char buffer[BUFSIZ+1];
 
   /* Créer le pipe */
   int fd[2];
   pipe(fd);
 
   /* Écrire dans le pipe */
   write(fd[1], "Hello World\n", strlen("Hello World\n"));
 
   /* Lire le pipre et imprimer la valeure lue. */
   read(fd[0], buffer, BUFSIZ);
   printf("%s", buffer);
  }

  La fonction "pipe(fd)" va réserver deux descripteurs de fichiers dans le tableau fd, "fd[0]" pour l'extrémité à lire et "fd[1]" pour l'extrémité à écrire. 
```

### [:link:](https://www.rozmichelle.com/pipes-forks-dups/)
Utility of File Descriptor, 


## References

- [Command line arguments](https://www.geeksforgeeks.org/command-line-arguments-in-c-cpp/)
- [Introduction to command shell](https://datacarpentry.org/shell-genomics/01-introduction/)

### Not used

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