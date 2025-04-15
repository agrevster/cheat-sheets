# Linux Command Guide
*This guide will discuss basic Linux commands, their function, as well as how and when to execute them.*
> "Linux is an open-source operating system that's used in many devices, including servers, computers, and smart devices" ~ Google
----------

### Some Linux features to be aware of
1. Commands, as well as files, are case sensitive `rm` **≠** `RM`.
2. Paths
    - Paths are broken into two sections:
        1. Relative paths
            Begin with **.** 
            - `./notes.txt` - The file named notes.txt in the current directory *(directory is what Linux calls folders)*
            - `.` - The current directory. 
            - `../`- One directory up from the current one. *(The directory that the current one is inside of)* 
            - `../conf`- The file or directory named "conf" in the folder above the working directory.
            - `~/Documents/` - The documents folder found within the current logged-in user's home directory. *(Think of `~` as /home/USERNAME)* 
            
        2. Absolute paths
            - `/var/log/syslog` - This is an absolute path because it begins with `/`
            - It points to the `syslog` file, a file that stores system logs.
            - `/home/username/Documents/report.txt` - This is also an absolute path
3. Everything is a file
    - `/dev/sda` contains info on your hard drive.
    - `/proc/cpuinfo` contains CPU info.
4. To run something as the root user run the `sudo` command before the command you want to run.
    - **WARNING:** Be very careful with the commands that you run with `sudo` as you are running them with full privilege. 
5. Terminal shortcuts
    | Key | Job |
    | -------------- | --------------- |
    | `<TAB>` | tries to complete the command you are typing with autocomplete.|
    | `<UP ARROW>` | Goes to the previously run command. |
    | `<DOWN ARROR>` | Goes to the command run after the previously ran command. |
    | `<CTRL> + C` | stops the current program |
6. Files beginning with `.` are hidden. 
    - Use `ls -a` to show them.
    

## Commands


*Notice how each new part is separated by a space...*
```bash
ls -n /bin
        ^ arguments
    ^ flags sometimes called options
^ command

```

### File and directory operations
- Nearly all these commands take in at least one file as the first argument.
```bash
command (flags) file file2?
```


| Command | Use                                                       | Extras and Tips                                                                                                                                                        |
|---------|-----------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `ls`    | List the files and directories in the current directory   | `-a` (shows hidden files) <br> `-l` (shows file permission info)                                                                                                       |
| `cd`    | Changes the current directory to a directory you specify. | Learn about file paths [here]()                                                                                                                                        |
| `pwd`   | Prints out the current working directory _(cwd)_.         |                                                                                                                                                                        |
| `mkdir` | Creates a new directory with a given name.                | Ex: `mkdir photos`. <br> `-p` to create multiple at the same time. Ex: `mkdir -p photos/cats`                                                                          |
| `touch` | Creates an empty file with the given name .               | This works with multiple files by default. `touch file1 file2 file3`                                                                                                   |
| `rm`    | Removes a file with a given name.                         | `-r` removes the directory and all of its contents if a directory is specified.                                                                                        |
| `rmdir` | Removes an empty directory with a given name.             | Use `rm -r` if you want to remove a directory and its files.                                                                                                           |
| `mv`    | Moves a file or directory.                                | Ex: `mv ./file.txt ../files/file.txt`                                                                                                                                  |
| `cp`    | Coppies a file.                                           | Ex: `cp ./file.txt ./file_backup.txt` <br>`-r` copies directories and files.                                                                                           |
| `cat`   | Prints out the contents of a file to the command line.    |                                                                                                                                                                        |
| `nano`  | Opens the nano editor to make changes to the given file.. | [How to Geek’s guide to nano.](https://www.howtogeek.com/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/) <br> *May not be installed by default* |


