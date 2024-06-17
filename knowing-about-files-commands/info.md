---
description: info linux command cheatsheet by Thamizhiniyan C S
---

# info

## Introduction

This command is used to read the documentations of commands in the Info Format. It's an alternative to the man page. The info command reads the info files, which are stored as nodes in tree structure. Each info file contains hyperlinks to the next node. Using hyperlinks another nodes can be accessed.

***

## Syntax

`info [OPTION]... [MENU-ITEM...]`

***

## Important Flags

| Flag                        | Description                                   |
| --------------------------- | --------------------------------------------- |
| `-a, –all`                  | Use all matching manuals.                     |
| `-k, –apropos=STRING`       | Look up STRING in all indices of all manuals. |
| `-d, –directory=DIR`        | Add DIR to INFOPATH.                          |
| `-f, –file=MANUAL`          | Specify Info manual to visit.                 |
| `-h, –help`                 | Display this help and exit.                   |
| `-n, –node=NODENAME`        | Specify nodes in first visited Info file.     |
| `-o, –output=FILE`          | Output selected nodes to FILE.                |
| `-O, –show-options, –usage` | Go to command-line options node.              |
| `-v, –variable VAR=VALUE`   | Assign VALUE to Info variable VAR.            |
| `–version`                  | Display version information and exit.         |
| `-w, –where, –location`     | Print physical location of Info file.         |

***

## Interactive Mode Commands

| Command                 | Description                                                                |
| ----------------------- | -------------------------------------------------------------------------- |
| `?`                     | Display command help                                                       |
| `PAGE UP or BACKSPACE`  | Display previous page                                                      |
| `PAGE DOWN or spacebar` | Display next page                                                          |
| `n`                     | Next—display the next node                                                 |
| `p`                     | Previous—display the previous node                                         |
| `U`                     | Up—display the parent node of the currently displayed node, usually a menu |
| `ENTER`                 | Follow the hyperlink at the cursor location                                |
| `Q`                     | Quit                                                                       |

## Examples

| Command                                                                                                                | Description                                                                              |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info
</code></pre>                             | show top-level dir menu                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info -a ls
</code></pre>                       | It uses all matching manuals and displays them for a particular command.                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info -k ls
</code></pre>                       | It looks up STRING in all indices of all manuals and then displays the same.             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info -d ls
</code></pre>                       | It adds DIR to INFOPATH and also displays the same.                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info -O ls
</code></pre>                       | It goes to the command-line options node for a particular command and displays the same. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info -w ls
</code></pre>                       | It prints the physical location of the Info file.                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man info
</code></pre>                         | To check the manual page of the info command.                                            |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info --help
</code></pre>                      | To check the help page of the info command.                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info info-stnd
</code></pre>                   | show the manual for this Info program                                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info emacs
</code></pre>                       | start at emacs node from top-level dir                                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info emacs buffers
</code></pre>               | select buffers menu entry in emacs manual                                                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info emacs -n Files
</code></pre>              | start at Files node within emacs manual                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info '(emacs)Files'
</code></pre>              | alternative way to start at Files node                                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info --show-options emacs
</code></pre>        | start at node with emacs' command line options                                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info --subnodes -o out.txt emacs
</code></pre> | dump entire emacs manual to out.txt                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">info -f ./foo.info
</code></pre>               | show file ./foo.info, not searching dir                                                  |
