---
description: ls linux command cheatsheet by Thamizhiniyan C S
---

# ls

## Introduction

Ls is short for “list”. This command lists information about directories and any type of files in the working directory.

***

## Syntax

`ls [OPTION]... [FILE]...`

***

## Important Flags

| Flag | Description                                                                                                                                                             |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-a` | do not ignore entries starting with .                                                                                                                                   |
| `-A` | do not list implied . and ..                                                                                                                                            |
| `-b` | print C-style escapes for nongraphic characters                                                                                                                         |
| `-B` | do not list implied entries ending with \~                                                                                                                              |
| `-c` | with -lt: sort by, and show, ctime (time of last modification of file status information); with -l: show ctime and sort by name; otherwise: sort by ctime, newest first |
| `-C` | list entries by columns                                                                                                                                                 |
| `-d` | list directories themselves, not their contents                                                                                                                         |
| `-D` | generate output designed for Emacs' dired mode                                                                                                                          |
| `-f` | list all entries in directory order                                                                                                                                     |
| `-F` | Add “/” at the end of each directory for distinguishing between files and directories                                                                                   |
| `-g` | like -l, but do not list owner                                                                                                                                          |
| `-G` | in a long listing, don't print group names                                                                                                                              |
| `-h` | with -l and -s, print sizes like 1K 234M 2G etc.                                                                                                                        |
| `-H` | follow symbolic links listed on the command line                                                                                                                        |
| `-i` | print the index number of each file                                                                                                                                     |
| `-I` | do not list implied entries matching shell PATTERN                                                                                                                      |
| `-k` | default to 1024-byte blocks for file system usage                                                                                                                       |
| `-l` | use a long listing format                                                                                                                                               |
| `-L` | when showing file information for a symbolic link, show information for the file the link references rather than for the link itself                                    |
| `-m` | fill width with a comma separated list of entries                                                                                                                       |
| `-n` | like -l, but list numeric user and group IDs                                                                                                                            |
| `-N` | print entry names without quoting                                                                                                                                       |
| `-o` | like -l, but do not list group information                                                                                                                              |
| `-p` | append / indicator to directories                                                                                                                                       |
| `-q` | print ? instead of nongraphic characters                                                                                                                                |
| `-Q` | enclose entry names in double quotes                                                                                                                                    |
| `-r` | reverse order while sorting                                                                                                                                             |
| `-R` | list subdirectories recursively                                                                                                                                         |
| `-s` | print the allocated size of each file, in blocks                                                                                                                        |
| `-S` | sort by file size, largest first                                                                                                                                        |
| `-t` | sort by time, newest first; see --time                                                                                                                                  |
| `-T` | assume tab stops at each COLS instead of 8                                                                                                                              |
| `-u` | with -lt: sort by, and show, access time                                                                                                                                |
| `-U` | do not sort; list entries in directory order                                                                                                                            |
| `-v` | natural sort of (version) numbers within text                                                                                                                           |
| `-w` | set output width to COLS. 0 means no limit                                                                                                                              |
| `-x` | list entries by lines instead of by columns                                                                                                                             |
| `-X` | sort alphabetically by entry extension                                                                                                                                  |
| `-Z` | print any security context of each file                                                                                                                                 |
| `-1` | list one file per line                                                                                                                                                  |

***

## Examples

| Command   | Description                                                                                               |
| --------- | --------------------------------------------------------------------------------------------------------- |
| `ls -F`   | Add “/” at the end of each directory for distinguishing between files and directories                     |
| `ls -m`   | Prints out directories and files separated by a comma                                                     |
| `ls -Q`   | Add quotation marks to all directories and files                                                          |
| `ls -i`   | To get the Inode (index node) number of all directories and files                                         |
| `ls -r`   | Sort directories and files in the reverse order                                                           |
| `ls -t`   | Sort directories and files by time and date of creation or modification                                   |
| `ls -X`   | Sort directories and files alphabetically by entry extension                                              |
| `ls -a`   | View hidden files                                                                                         |
| `ls -l`   | To print out a long listing format of files and directories                                               |
| `ls -la`  | Displays information about the user, size of the file, and date and time of modification of all the files |
| `ls -R`   | Directory Tree / Recursively listing directories                                                          |
| `ls -n`   | List UID and GID of Files                                                                                 |
| `ls -lh`  | Display Files in Human Readable Format                                                                    |
| `ls -ltr` | View Reverse Output Order by Date                                                                         |
| `ls -lS`  | List Files by Size                                                                                        |
| `ls -ld`  | To check information about the directory only                                                             |
