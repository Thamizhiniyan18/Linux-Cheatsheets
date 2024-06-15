---
description: tree linux command cheatsheet by Thamizhiniyan C S
---

# tree

## Introduction

This command is used to list contents of directories in a tree-like format.

***

## Syntax

`tree [-acdfghilnpqrstuvxACDFJQNSUX] [-L level [-R]] [-H baseHREF] [-T title] [-o filename] [-P pattern] [-I pattern] [--gitignore] [--git‐ file[=]file] [--matchdirs] [--metafirst] [--ignore-case] [--nolinks] [--hintro[=]file] [--houtro[=]file] [--inodes] [--device] [--sort[=]name] [--dirsfirst] [--filesfirst] [--filelimit #] [--si] [--du] [--prune] [--charset[=]X] [--timefmt[=]format] [--fromfile] [--fflinks] [--info] [--infofile[=]file] [--noreport] [--version] [--help] [--] [directory ...]`

***

## Important Flags

### Listing Options

| Flag            | Description                                                  |
| --------------- | ------------------------------------------------------------ |
| `-a`            | All files are listed.                                        |
| `-d`            | List directories only.                                       |
| `-l`            | Follow symbolic links like directories.                      |
| `-f`            | Print the full path prefix for each file.                    |
| `-x`            | Stay on current filesystem only.                             |
| `-L level`      | Descend only level directories deep.                         |
| `-R`            | Rerun tree when max dir level reached.                       |
| `-P pattern`    | List only those files that match the pattern given.          |
| `-I pattern`    | Do not list files that match the given pattern.              |
| `--gitignore`   | Filter by using .gitignore files.                            |
| `--gitfile X`   | Explicitly read gitignore file.                              |
| `--ignore-case` | Ignore case when pattern matching.                           |
| `--matchdirs`   | Include directory names in -P pattern matching.              |
| `--metafirst`   | Print meta-data at the beginning of each line.               |
| `--prune`       | Prune empty directories from the output.                     |
| `--info`        | Print information about files found in .info files.          |
| `--infofile X`  | Explicitly read info file.                                   |
| `--noreport`    | Turn off file/directory count at end of tree listing.        |
| `--charset X`   | Use charset X for terminal/HTML and indentation line output. |
| `--filelimit #` | Do not descend dirs with more than # files in them.          |
| `-o filename`   | Output to file instead of stdout.                            |

### File Options

| Flag        | Description                                                |
| ----------- | ---------------------------------------------------------- |
| `-q`        | Print non-printable characters as '?'.                     |
| `-N`        | Print non-printable characters as is.                      |
| `-Q`        | Quote filenames with double quotes.                        |
| `-p`        | Print the protections for each file.                       |
| `-u`        | Displays file owner or UID number.                         |
| `-g`        | Displays file group owner or GID number.                   |
| `-s`        | Print the size in bytes of each file.                      |
| `-h`        | Print the size in a more human readable way.               |
| `--si`      | Like -h, but use in SI units (powers of 1000).             |
| `--du`      | Compute size of directories by their contents.             |
| `-D`        | Print the date of last modification or (-c) status change. |
| `--timefmt` | Print and format time according to the format .            |
| `-F`        | Appends '/', '=', '\*', '@', '\|' or '>' as per ls -F.     |
| `--inodes`  | Print inode number of each file.                           |
| `--device`  | Print device ID number to which each file belongs.         |

### Sorting Options

| Flag           | Description                                  |
| -------------- | -------------------------------------------- |
| `-v`           | Sort files alphanumerically by version.      |
| `-t`           | Sort files by last modification time.        |
| `-c`           | Sort files by last status change time.       |
| `-U`           | Leave files unsorted.                        |
| `-r`           | Reverse the order of the sort.               |
| `--dirsfirst`  | List directories before files (-U disables). |
| `--filesfirst` | List files before directories (-U disables). |
| `--sort X`     | Select sort: name,version,size,mtime,ctime.  |

### Graphics Options

| Flag | Description                                            |
| ---- | ------------------------------------------------------ |
| `-i` | Don't print indentation lines.                         |
| `-A` | Print ANSI lines graphic indentation lines.            |
| `-S` | Print with CP437 (console) graphics indentation lines. |
| `-n` | Turn colorization off always (-C overrides).           |
| `-C` | Turn colorization on always.                           |

### XML/HTML/JSON Options

| Flag          | Description                                               |
| ------------- | --------------------------------------------------------- |
| `-X`          | Prints out an XML representation of the tree.             |
| `-J`          | Prints out an JSON representation of the tree.            |
| `-H baseHREF` | Prints out HTML format with baseHREF as top directory.    |
| `-T string`   | Replace the default HTML title and H1 header with string. |
| `--nolinks`   | Turn off hyperlinks in HTML output.                       |
| `--hintro X`  | Use file X as the HTML intro.                             |
| `--houtro X`  | Use file X as the HTML outro.                             |

### Input Options

| Flag         | Description                                     |
| ------------ | ----------------------------------------------- |
| `--fromfile` | Reads paths from files (.=stdin)                |
| `--fflinks`  | Process link information when using --fromfile. |

### Misc Options

| Flag        | Description                                 |
| ----------- | ------------------------------------------- |
| `--version` | Print version and exit.                     |
| `--help`    | Print usage and this help message and exit. |
| `--`        | Options processing terminator.              |

***

## Examples

| Command                                                                                                            | Description                                                                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree
</code></pre>                         | Displays the tree structure of our current directory, showing all the files, folders, and sub-folders.                                                                                            |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -a
</code></pre>                      | Display hidden files along with other files using tree. In the tree, the folders and files which are starting from a '.' are the hidden folders and files.                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -a [DirectoryName/Path]
</code></pre> | Display contents of a specific directory.                                                                                                                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -d
</code></pre>                      | Display only directory listing through tree (print only directories).                                                                                                                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -f
</code></pre>                      | Display full path prefix of files and folders using tree. It is mainly useful when we need to know what exists where.                                                                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -s
</code></pre>                      | Display size of files and folders using tree. With the help of the 's' flag, we can check which memory items consume more space on our system and getting rid of needless ones.                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -p
</code></pre>                      | Display read-write permission of files and folders using tree. Thus, before performing operation on a file and folder, we can first see and edit the permissions that exist on a particular item. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -L[n]
</code></pre>                   | List folder contents till a certain level/depth through tree. This command will only show the sub-directories (using -d flag) of the present directory not the additional expanded tree.          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -cD TargetDirectory
</code></pre>     | Sort files based on first modification                                                                                                                                                            |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -cDr TargetDirectory
</code></pre>    | Sort files based on the last modification                                                                                                                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree -P sample* .
</code></pre>            | List files with entered pattern                                                                                                                                                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree --filelimit 3 ./Desktop
</code></pre> | List those directories which have greater ‘N’ number of files/directories                                                                                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">tree --device ./Desktop
</code></pre>      | Prints the device number to which the file or directory belongs.                                                                                                                                  |
