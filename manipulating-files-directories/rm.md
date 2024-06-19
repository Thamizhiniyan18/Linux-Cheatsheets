---
description: rm linux command cheatsheet by Thamizhiniyan C S
---

# rm

## Introduction

The `rm` command is used to remove files or directories.

***

## Syntax

`rm [OPTION]... [FILE]...`

***

## Important Flags

| Flag        | Description                                                                      |
| ----------- | -------------------------------------------------------------------------------- |
| `-f`        | Forces the removal of all files or directories.                                  |
| `-i`        | Prompts for confirmation before removing.                                        |
| `-I`        | Prompts once before removing more than three files or when removing recursively. |
| `-r`        | Removes directories and their content recursively.                               |
| `-d`        | Removes empty directories.                                                       |
| `-v`        | Provides a verbose output.                                                       |
| `--help`    | Displays the help text.                                                          |
| `--version` | Displays the command version.                                                    |

***

## Examples

| Command                                                                                                      | Description                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm a.txt
</code></pre>               | Removing one file at a time.                                                                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm b.txt c.txt
</code></pre>         | Removing more than one file at a time.                                                                                               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -d Example
</code></pre>          | To remove an empty directory.                                                                                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -- [directory name]
</code></pre> | To remove a directory whose name starts with a hyphen (-).                                                                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -- -file.txt
</code></pre>        | Removes a file whose name starts with a hyphen (-).                                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -r Example
</code></pre>          | To delete a directory that contains subdirectories and files (Recursive Deletion)                                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -r -v Example
</code></pre>       | To delete a directory that contains subdirectories and files (Recursive Deletion), and the -v flag to list each step of the process. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -r *
</code></pre>                | -r : Deletes all files and sub-directories recursively in the parent directory.                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -i d.txt
</code></pre>            | Asks for confirmation before removing each file (Interactive Deletion).                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -d -i Example
</code></pre>       | Use the -i option to display a prompt asking for confirmation before removing a directory.                                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -f e.txt
</code></pre>            | Overrides write protection and removes the file forcefully (Force Deletion).                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -d Example
</code></pre>          | Remove a write-protected directory.                                                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -d -f Example
</code></pre>       | To avoid confirmation when deleting a directory.                                                                                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sudo rm -d Example
</code></pre>     | Elevate command privileges to remove a write-protected directory.                                                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm -rf 
</code></pre>                | Use this command to remove a write-protected directory that contains other files and directories.                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm --version
</code></pre>           | Displays the version of rm currently running on the system.                                                                          |
