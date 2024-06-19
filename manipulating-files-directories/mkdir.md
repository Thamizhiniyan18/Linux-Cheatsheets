---
description: mkdir linux command cheatsheet by Thamizhiniyan C S
---

# mkdir

## Introduction

mkdir ( make directory ) is used to create directory(ies), if they don't exist already.

***

## Syntax

`mkdir [OPTION]... DIRECTORY...`

***

## Important Flags

| Flag                    | Description                                                              |
| ----------------------- | ------------------------------------------------------------------------ |
| `-p`                    | Creates parent directories if they don't exist.                          |
| `-m a=[rwx] [dir_name]` | Sets the file modes, i.e., permissions, for the new directory.           |
| `-v`                    | Displays a message for each created directory.                           |
| `--version`             | Displays the version number and information about the license and exits. |
| `-Z`                    | Sets the SELinux security context for directories.                       |
| `-help`                 | Displays help with information about mkdir options.                      |

***

## Examples

| Command                                                                                                                | Description                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir Linux
</code></pre>                      | To create a single directory named Linux                                                                                                                                            |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir "My Documents"
</code></pre>             | To create a directory with spaces in its name, enclose the entire directory name in quotes.                                                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir /tmp/example
</code></pre>               | To create a directory or directories in a specific location other than your current working directory, specify the full directory path.                                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir my_folder/sub_folder
</code></pre>       | This command creates a directory structure with “my\_folder” as the parent directory and “sub\_folder” as its subdirectory.                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir dir1 dir2 dir3
</code></pre>             | To create multiple directories at once, list the directory names separated by a space.                                                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir {test1,test2,test3}
</code></pre>        | Use mkdir with curly brackets to create multiple directories without spaces.                                                                                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir dir{1..15}
</code></pre>                 | Create a batch of directories starting with the same pattern, from dir1 to dir15.                                                                                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir $USER
</code></pre>                      | mkdir allows you to use environment variables in directory names. This example creates a directory with the current user being the directory name.                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir –p Linux/dirtest1/dirtest2
</code></pre> | To build a structure with multiple subdirectories. This ensures that mkdir adds any missing parent directories in the process. If the directories exist, no error is specified.     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir -p first/second/third
</code></pre>      | If the first and second directories do not exist, due to the -p option, mkdir will create these directories. If the -p option is not specified, an error is returned.               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir –m 777 DirM
</code></pre>                | To add all permissions for all users when creating a directory, specify the -m option with 777.                                                                                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir -m a=rwx [directories]
</code></pre>     | This option is used to set the file modes, i.e. permissions, for the created directories.                                                                                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir -m 755 public
</code></pre>              | Use the ‘-m’ option to set specific permissions for a directory. This command sets read, write, and execute permissions for the owner, and read and execute permissions for others. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir -v [directories]
</code></pre>           | To see the details of the mkdir process. It displays a message for every directory created.                                                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir --help
</code></pre>                     | It displays help-related information and exits.                                                                                                                                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mkdir --version
</code></pre>                  | It displays the version number, some information regarding the license and exits.                                                                                                   |
