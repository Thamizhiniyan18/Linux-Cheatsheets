---
description: apropos linux command cheatsheet by Thamizhiniyan C S
---

# apropos

## Introduction

The `apropos` command is used to search the manual page names and descriptions.

***

## Syntax

`apropos [-dalv?V] [-e|-w|-r] [-s list] [-m system[,...]] [-M path] [-L locale] [-C file] keyword ...`

***

## Important Flags

| Flag                                         | Description                                                                                 |
| -------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `whatis -d, --debug`                         | Prints debugging messages.                                                                  |
| `whatis -v, --verbose`                       | Print verbose warning messages.                                                             |
| `whatis -e, --exact`                         | Search each keyword for exact match.                                                        |
| `whatis -r, --regex`                         | Interpret each keyword as a regex.                                                          |
| `whatis -w, --wildcard`                      | The keyword(s) contain wildcards.                                                           |
| `whatis -a, --and`                           | Require all keywords to match.                                                              |
| `whatis -l, --long`                          | Do not trim output to terminal width.                                                       |
| `whatis -C, --config-file=FILE`              | Uses user-configuration files instead of the $MANPATH.                                      |
| `whatis -L, --locale=LOCALE`                 | Define the locale for this search.                                                          |
| `whatis -m, --systems=SYSTEM`                | Use manual pages from other systems. Looks for man page descriptions from other OSs.        |
| `whatis -M, --manpath=PATH`                  | Sets the search path to PATH rather than the default $MANPATH.                              |
| `whatis -s, --sections=LIST, --section=LIST` | Search only these sections (colon-separated). Searches only in specific man pages sections. |
| `whatis -?, --help`                          | Give this help list.                                                                        |
| `whatis --usage`                             | Give a short usage message.                                                                 |
| `whatis -V, --version`                       | Print program version.                                                                      |

***

## Examples

| Command                                                                                                                                          | Description                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos list
</code></pre>                                               | The apropos primary usage is to find a single keyword in man pages.                                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos -a list directory
</code></pre>                                  | Add another variable to narrow down the matches.                                                                       |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos "list directory"
</code></pre>                                   | Achieve a similar effect without \`-a\` by encasing keywords in double quotes.                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos delete terminate remove
</code></pre>                            | Find Either of Two / More Parameters                                                                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos -e set
</code></pre>                                             | Find Exact Match                                                                                                       |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos -s 1,8 list
</code></pre>                                        | Search Specific Sections                                                                                               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos '^list'
</code></pre>                                            | Use Regex Symbols                                                                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos "zip(note|cloak|info)"
</code></pre>                             | Use regex to conduct an even more specific search.                                                                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos -a -s 3,8 "^list" "(implementation|devices|users)"
</code></pre> | As the output shows, each line includes list at the beginning, belongs to section 3 or 8, and has one of the keywords. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">apropos list -l
</code></pre>                                            | To avoid the trimming of descriptions in apropos command output                                                        |
