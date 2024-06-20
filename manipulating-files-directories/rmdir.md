---
description: rmdir linux command cheatsheet by Thamizhiniyan C S
---

# rmdir

## Introduction

This command is used to remove the DIRECTORY(ies), if they are empty.

***

## Syntax

`rmdir [OPTION]... DIRECTORY...`

***

## Important Flags

| Flag                         | Description                                                                |
| ---------------------------- | -------------------------------------------------------------------------- |
| `--ignore-fail-on-non-empty` | Doesn't show an error message when trying to remove a non-empty directory. |
| `-p`                         | Removes the directory along with its parent in the hierarchy.              |
| `-v`                         | Provides a verbose output.                                                 |
| `--help`                     | Displays help text.                                                        |
| `--version`                  | Displays the command version.                                              |

***

## Examples

| Command                                                                                                                          | Description                                                                                           |
| -------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir mydir1 mydir2 mydir3 .....
</code></pre>           | Removes multiple directories using the basic rmdir command.                                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir LINUX INFO DETAIL
</code></pre>                    | Removes the LINUX, INFO, and DETAIL directories.                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir -p mydir1/mydir2/mydir3/...../mydirN
</code></pre> | Deletes a directory, including all subdirectories.                                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir -p LINUX/mydir1/mydir2/mydir3
</code></pre>        | Deletes the LINUX directory, including all its ancestors.                                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir -p -v Example/Test
</code></pre>                   | Removes a subdirectory and its hierarchical parent and lists each step of the process.                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir -v dir1 dir2 dir3
</code></pre>                    | Displays a message after removing the specified directories.                                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir -v LINUX INFO DETAIL
</code></pre>                 | Deletes the LINUX, INFO, and DETAIL directories and displays a message after each removal.            |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir -v LINUX*
</code></pre>                            | Deletes all directories that contain "LINUX" in their name and displays a message after each removal. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir -v Example/Test Example
</code></pre>              | Removes multiple directories in reverse order of hierarchy and lists each step of the process.        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir -v Example*
</code></pre>                          | Removes multiple directories with similar names using wildcards and lists each step of the process.   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rmdir --ignore-fail-on-non-empty LINUX
</code></pre>     | Ignores errors due to non-empty directories when attempting to remove the LINUX directory.            |
