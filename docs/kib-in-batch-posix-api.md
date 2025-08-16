# KIB in Batch POSIX API

KIB in Batch also reimplements parts of the POSIX API, allowing compiling and running of Unix programs that adhere to the implemented functions.

## 1. Compiling and Running Unix Programs

It is rather simple, these are the steps:

* Install a C compiler on your host that supports the -I flag. I recommend Clang.
* Open a KIB in Batch shell and run the following:

```bash
clang -I/usr/include -o unix_program.exe unix_program.c
./unix_program
```

## 2. Using APIs from Batch files

A select amount of APIs use Batch files as the backend. That means they can be called from batch files.

For example, to use the mkdir function, you can use the following:

```bat
@echo off
call "%USERPROFILE%\kib\usr\lib\posix\mkdir.bat" my_directory 0755 & rem Mode is ignored, only there for compatibility
```

## 3. Using APIs from C programs

Here is an example of a C program using some APIs:

```c
#include <stdio.h>
#include <unistd.h>
#include <sys/stat.h>

int main() {
    char cwd[4096];

    if (getcwd(cwd, sizeof(cwd)) != NULL) {
        printf("Current working directory: %s\n", cwd);
    } else {
        perror("getcwd() error");   
        return 1;
    }

    // Create a new directory
    printf("Creating demo_directory... ");
    mkdir("demo_directory", 0777);
    printf("Created demo_directory\n");

    // Change to demo_directory
    printf("Changing to demo_directory... ");
    if (chdir("demo_directory") != 0) {
        perror("chdir() error");
        return 1;
    } else {
        printf("Changed to demo_directory\n");
        char cwd2[4096];
        if (getcwd(cwd2, sizeof(cwd2)) != NULL) {
            printf("Current working directory: %s\n", cwd2);
        } else {
            perror("getcwd() error");
        }
    }

    printf("Sleeping for 2 seconds... ");
    sleep(2);
    printf("Slept for 2 seconds\n");

    return 0;
}
```

Compile it using the steps defined in 1.
