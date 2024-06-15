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

## Important Flags

| Flag                  | Description                                                                                                                                 |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `-L, --dereference`   | follow links                                                                                                                                |
| `-f, --file-system`   | display file system status instead of file status                                                                                           |
| `--cached=MODE`       | specify how to use cached attributes; useful on remote file systems. See MODE below                                                         |
| `-c, --format=FORMAT` | use the specified FORMAT instead of the default; output a newline after each use of FORMAT                                                  |
| `--printf=FORMAT`     | like --format, but interpret backslash escapes, and do not output a mandatory trailing newline; if you want a newline, include \n in FORMAT |
| `-t, --terse`         | print the information in terse form                                                                                                         |
| `--help`              | display this help and exit                                                                                                                  |
| `--version`           | output version information and exit                                                                                                         |

### MODE values

| Flag      | Description                                             |
| --------- | ------------------------------------------------------- |
| `always`  | will use cached attributes if available, while          |
| `never`   | will try to synchronize with the latest attributes, and |
| `default` | will leave it up to the underlying file system.         |

***

## Examples

| Command                                                                                                               | Description                                                                                                                      |
| --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">stat -f MyFile
</code></pre>                  | show details about the file system the file \_MyFile\_ is on                                                                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">stat -f /home
</code></pre>                   | To print information about the file system a particular \[directory]\(https://phoenixnap.com/glossary/what-is-a-directory) is on |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">stat MyFile MyFile2
</code></pre>             | To print info on multiple files                                                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">stat /usr/local/bin/vim
</code></pre>         | To print info about the symlink                                                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">stat -L stat /usr/local/bin/vim
</code></pre> | To get information about the file the symlink points to                                                                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">stat -t MyFile
</code></pre>                  | To print an one line, space separated output of all details                                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">stat -c=%i MyFile
</code></pre>               | Prints only the \_MyFile\_ inode number                                                                                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">stat --printf='%i\n' MyFile
</code></pre>     | Prints only the \_MyFile\_ inode number                                                                                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">stat --format=%F:%u:%y MyFile
</code></pre>   | Prints the file type, user ID, and last modified ti                                                                              |

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
