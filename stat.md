---
description: stat linux command cheatsheet by Thamizhiniyan C S
---

# stat

## Introduction

The **`stat`** command prints details about [files](https://phoenixnap.com/kb/linux-file-permissions) and [file systems](https://phoenixnap.com/kb/linux-file-system).

***

## Syntax

`stat [arguments] [filename]`

`stat [argument] = "FORMAT" [filename]`

***

## Examples

| Command                           | Description                                                                                                                    |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| `stat -f MyFile`                  | show details about the file system the file _MyFile_ is on                                                                     |
| `stat -f /home`                   | To print information about the file system a particular [directory](https://phoenixnap.com/glossary/what-is-a-directory) is on |
| `stat MyFile MyFile2`             | To print info on multiple files                                                                                                |
| `stat /usr/local/bin/vim`         | To print info about the symlink                                                                                                |
| `stat -L stat /usr/local/bin/vim` | To get information about the file the symlink points to                                                                        |
| `stat -t MyFile`                  | To print an one line, space separted output of all details                                                                     |
| `stat -c=%i MyFile`               | Prints only the _MyFile_ inode number                                                                                          |
| `stat --printf='%i\n' MyFile`     | Prints only the _MyFile_ inode number                                                                                          |
| `stat --format=%F:%u:%y MyFile`   | Prints the file type, user ID, and last modified time                                                                          |

***

## Customize Output Format <a href="#ftoc-heading-7" id="ftoc-heading-7"></a>

The two arguments used to customize the **`stat`** output are:

* **`-c`** **(`--format`).** Tells **`stat`** to use the specified format string instead of the default format.
* &#x20;**`--printf`.** Similar to **`-c`**, but it allows the use of backslashes in the format string.

\
The following table lists the most commonly used format operands for files and directories:&#x20;

| Operand | Files                                                     | File Systems                             |
| ------- | --------------------------------------------------------- | ---------------------------------------- |
| %a      | Access rights in octal format.                            | Free blocks available to non-superuser.  |
| %A      | Access rights in human-readable form.                     |  /                                       |
| %b      | Number of blocks allocated.                               | Total data blocks in a file system.      |
| %B      | The size in bytes of each block.                          |  /                                       |
| %c      |  /                                                        | Total data blocks in a file system.      |
| %C      | The raw mode in hex.                                      |  /                                       |
| %d      | Device number in decimal.                                 | Total file nodes in a file system.       |
| %D      | Device number in hex.                                     |  /                                       |
| %f      | Raw mode in hex.                                          | Free file nodes in a file system.        |
| %F      | File type.                                                |  /                                       |
| %g      | Group owner ID.                                           |  /                                       |
| %G      | Group owner name.                                         |  /                                       |
| %h      | Hard links number.                                        |  /                                       |
| %i      | Inode number.                                             | File system ID in hex.                   |
| %l      |  /                                                        | Free blocks in the file system.          |
| %m      | Mount point.                                              |                                          |
| %n      | File name.                                                | File name.                               |
| %N      | Quoted file name with dereferencing if a symlink is used. | /                                        |
| %o      | Optimal I/O transfer size hint.                           | /                                        |
| %s      | Total size.                                               | Block size.                              |
| %S      |  /                                                        | Fundamental block size.                  |
| %t      | Major device type in hex.                                 | File system type in hex.                 |
| %T      | Minor device type in hex.                                 | File system type in human-readable form. |
| %u      | User ID.                                                  |  /                                       |
| %U      | User name.                                                |  /                                       |
| %w      | File birth time, human-readable.                          |  /                                       |
| %W      | File birth time, seconds since Epoch.                     |  /                                       |
| %x      | Last access time, human-readable.                         |  /                                       |
| %X      | Last access time, seconds since Epoch.                    |  /                                       |
| %y      | Last data modification time, human-readable.              |  /                                       |
| %Y      | Last data modification time, seconds since Epoch.         |  /                                       |
| %z      | Last status change time, human-readable.                  |  /                                       |
| %Z      | Last status change time, seconds since Epoch.             |  /                                       |
