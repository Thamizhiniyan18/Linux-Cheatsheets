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

<table><thead><tr><th width="114">Flag</th><th>Description</th></tr></thead><tbody><tr><td><code>-a</code></td><td>do not ignore entries starting with .</td></tr><tr><td><code>-A</code></td><td>do not list implied . and ..</td></tr><tr><td><code>-b</code></td><td>print C-style escapes for nongraphic characters</td></tr><tr><td><code>-B</code></td><td>do not list implied entries ending with ~</td></tr><tr><td><code>-c</code></td><td>with -lt: sort by, and show, ctime (time of last modification of file status information); with -l: show ctime and sort by name; otherwise: sort by ctime, newest first</td></tr><tr><td><code>-C</code></td><td>list entries by columns</td></tr><tr><td><code>-d</code></td><td>list directories themselves, not their contents</td></tr><tr><td><code>-D</code></td><td>generate output designed for Emacs' dired mode</td></tr><tr><td><code>-f</code></td><td>list all entries in directory order</td></tr><tr><td><code>-F</code></td><td>Add “/” at the end of each directory for distinguishing between files and directories</td></tr><tr><td><code>-g</code></td><td>like -l, but do not list owner</td></tr><tr><td><code>-G</code></td><td>in a long listing, don't print group names</td></tr><tr><td><code>-h</code></td><td>with -l and -s, print sizes like 1K 234M 2G etc.</td></tr><tr><td><code>-H</code></td><td>follow symbolic links listed on the command line</td></tr><tr><td><code>-i</code></td><td>print the index number of each file</td></tr><tr><td><code>-I</code></td><td>do not list implied entries matching shell PATTERN</td></tr><tr><td><code>-k</code></td><td>default to 1024-byte blocks for file system usage</td></tr><tr><td><code>-l</code></td><td>use a long listing format</td></tr><tr><td><code>-L</code></td><td>when showing file information for a symbolic link, show information for the file the link references rather than for the link itself</td></tr><tr><td><code>-m</code></td><td>fill width with a comma separated list of entries</td></tr><tr><td><code>-n</code></td><td>like -l, but list numeric user and group IDs</td></tr><tr><td><code>-N</code></td><td>print entry names without quoting</td></tr><tr><td><code>-o</code></td><td>like -l, but do not list group information</td></tr><tr><td><code>-p</code></td><td>append / indicator to directories</td></tr><tr><td><code>-q</code></td><td>print ? instead of nongraphic characters</td></tr><tr><td><code>-Q</code></td><td>enclose entry names in double quotes</td></tr><tr><td><code>-r</code></td><td>reverse order while sorting</td></tr><tr><td><code>-R</code></td><td>list subdirectories recursively</td></tr><tr><td><code>-s</code></td><td>print the allocated size of each file, in blocks</td></tr><tr><td><code>-S</code></td><td>sort by file size, largest first</td></tr><tr><td><code>-t</code></td><td>sort by time, newest first; see --time</td></tr><tr><td><code>-T</code></td><td>assume tab stops at each COLS instead of 8</td></tr><tr><td><code>-u</code></td><td>with -lt: sort by, and show, access time</td></tr><tr><td><code>-U</code></td><td>do not sort; list entries in directory order</td></tr><tr><td><code>-v</code></td><td>natural sort of (version) numbers within text</td></tr><tr><td><code>-w</code></td><td>set output width to COLS. 0 means no limit</td></tr><tr><td><code>-x</code></td><td>list entries by lines instead of by columns</td></tr><tr><td><code>-X</code></td><td>sort alphabetically by entry extension</td></tr><tr><td><code>-Z</code></td><td>print any security context of each file</td></tr><tr><td><code>-1</code></td><td>list one file per line</td></tr></tbody></table>

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
