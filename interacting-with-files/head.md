---
description: head linux command cheatsheet by Thamizhiniyan C S
---

# head

## Introduction

The head command is used to output the first part of files.

***

## Syntax

`head [OPTION]... [FILE]...`

***

## Important Flags

| Flag     | Description                                                     |
| -------- | --------------------------------------------------------------- |
| `-n num` | Prints the first ‘num’ lines instead of the first 10 lines.     |
| `-c num` | Prints the first ‘num’ bytes from the file specified.           |
| `-q`     | Suppresses printing filenames when more than one file is given. |
| `-v`     | Prints data from the specified file preceded by its filename.   |

***

## Examples

| Command                                                                                                              | Description                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">head -n 20 file.txt | tail -10
</code></pre> | To print lines between 10 and 20 in file.txt.                                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">ls -t | head -n 3
</code></pre>              | Pipe the output of ls command to head to show only the three most recently modified files or folders.                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">ls -t | head -n 3 | sort
</code></pre>       | Pipe the output of ls command to head and sort to display the three most recently used files or folders in alphabetical order. |
