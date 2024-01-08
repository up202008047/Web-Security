1. # **Week #4**

1. ## **Task 1**
- printenv/env prints out the environment variables

![](docs/Aspose.Words.40517748-ef6b-4ed2-a50a-804588372a59.001.png)

---

1. ## **Task 2**
- Compiled the program ‘myprintenv.c’ into two binaries, each differing on which process would print the environment variables (parent and child)
- Each program output is directed to different files (file.txt and file1.txt)
- Comparing the outputs with the ‘diff’ command, the environment variables for a parent and child process are the same

![](docs/Aspose.Words.40517748-ef6b-4ed2-a50a-804588372a59.002.png)

![](docs/Aspose.Words.40517748-ef6b-4ed2-a50a-804588372a59.003.png)

![](docs/Aspose.Words.40517748-ef6b-4ed2-a50a-804588372a59.004.png)

---

1. ## **Task 3**
- Compiled the program ‘myenv.c’ and ran it. There was no output, which can be explained by the fact that the ‘execve’ function starts a process and associates to it the array of environment variables given to it in the third argument, which was NULL pointer.
- When this argument is changed to ‘environ’, the output is now the parent’s process environment variables.

![](docs/Aspose.Words.40517748-ef6b-4ed2-a50a-804588372a59.005.png)

---

1. ## **Task 4**
- Created a program ‘system.c’, compiled and ran it. The output was the parent process’s environment variables, as expected, since the ‘system’ function uses ‘execl’, which in its turn calls ‘execve’ with the parent process’s EVs, which finallt executes /bin/sh with the argument passed to ‘system’

![](docs/Aspose.Words.40517748-ef6b-4ed2-a50a-804588372a59.006.png)

---

1. ## **Task 5**
- Created a program ‘setuid.c’, complied it and mode root its owner and transformed it into a Set-UID program through the instructions given.
- As a normal user, ran the program

![](docs/Aspose.Words.40517748-ef6b-4ed2-a50a-804588372a59.007.png)

![](docs/Aspose.Words.40517748-ef6b-4ed2-a50a-804588372a59.008.png)

---


1. ## **Task 6**

- After appending /home/seed to the PATH environment variable, we created new program to run ‘ls’ in that directory
- Changed it to our own malicious code, compiled the program and transformed it into a SET-UID program like we did in Task 5

![](docs/Aspose.Words.40517748-ef6b-4ed2-a50a-804588372a59.009.png)


---
