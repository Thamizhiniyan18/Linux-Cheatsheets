---
description: whatis linux command cheatsheet by Thamizhiniyan C S
---

# whatis

## Introduction

The `whatis` command is used to display one-line manual page descriptions.

***

## Syntax

`whatis [-dlv?V] [-r|-w] [-s list] [-m system[,...]] [-M path] [-L locale] [-C file] name ...`

***

## Important Flags

| Flag                                  | Description                                   |
| ------------------------------------- | --------------------------------------------- |
| `-d, --debug`                         | Emit debugging messages.                      |
| `-v, --verbose`                       | Print verbose warning messages.               |
| `-r, --regex`                         | Interpret each keyword as a regex.            |
| `-w, --wildcard`                      | The keyword(s) contain wildcards.             |
| `-l, --long`                          | Do not trim output to terminal width.         |
| `-C, --config-file=FILE`              | Use this user configuration file.             |
| `-L, --locale=LOCALE`                 | Define the locale for this search.            |
| `-m, --systems=SYSTEM`                | Use manual pages from other systems.          |
| `-M, --manpath=PATH`                  | Set search path for manual pages to PATH.     |
| `-s, --sections=LIST, --section=LIST` | Search only these sections (colon-separated). |
| `-?, --help`                          | Give this help list.                          |
| `--usage`                             | Give a short usage message.                   |
| `-V, --version`                       | Print program version.                        |

***

## Examples

| Command                                                                                                              | Description                                                                                                                                           |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -h
</code></pre>                      | Prints the help message.                                                                                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -d ls
</code></pre>                   | Prints the debugging information.                                                                                                                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -v ls
</code></pre>                   | Prints verbose warning messages.                                                                                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -r ls
</code></pre>                   | Supports regular expression searches.                                                                                                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -r '^ab'
</code></pre>                | Searches and displays short descriptions of commands and functions matching the regular expression '^ab'.                                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -r '^cd'
</code></pre>                | Searches and displays short descriptions of commands and functions matching the regular expression '^cd'.                                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -r 'cd$'
</code></pre>                | Searches and displays short descriptions of commands and functions matching the regular expression 'cd$'.                                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -w ls
</code></pre>                   | Enables wildcard searches using the specified pattern.                                                                                                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -w 'ab*'
</code></pre>                | Searches and displays short descriptions of commands and functions matching the wildcard pattern 'ab\*'.                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -w 'cd*'
</code></pre>                | Searches and displays short descriptions of commands and functions matching the wildcard pattern 'cd\*'.                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -l cat
</code></pre>                  | Displays long descriptions in addition to the summary.                                                                                                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -s 3 cat
</code></pre>                | Allows users to specify the sections from which to retrieve the information. By default, it searches all sections.                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -s "1","2" cat
</code></pre>          | Accesses information from sections 1 and 2 of the manual page for the cat command.                                                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -m NewOS rmdir
</code></pre>          | Accesses manual page names for other operating systems.                                                                                               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -m OS2 rmdir
</code></pre>            | Accesses the short description of the rmdir command from the OS2 manual pages.                                                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis cd -M --manpath=/lib/cd
</code></pre> | Specifies an alternate set of colon-delimited manual page hierarchies to search. It overrides the default value of the $MANPATH environment variable. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis rm -L locale
</code></pre>            | Temporarily overrides the determined locale value, allowing users to supply a locale string directly to the 'whatis' command.                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -C file
</code></pre>                 | Specifies a user configuration file for the 'whatis' command, overriding the default configuration file location \~/.manpath.                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -?
</code></pre>                      | Prints a help message.                                                                                                                                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis --usage
</code></pre>                 | Displays short information about the whatis command and exits.                                                                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis -V
</code></pre>                      | Displays version information.                                                                                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">whatis ssh-import-id
</code></pre>           | Displays the trimmed output of the ssh-import-id command.                                                                                             |
