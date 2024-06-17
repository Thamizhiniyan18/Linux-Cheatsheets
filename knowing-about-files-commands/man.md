---
description: man linux command cheatsheet by Thamizhiniyan C S
---

# man

## Introduction

The `man` command is used to display the command / program's documentation / manual page.

***

## Syntax

```bash
man [man options] [[section] page ...] ...
man -k [apropos options] regexp ...
man -K [man options] [section] term ...
man -f [whatis options] page ...
man -l [man options] file ...
man -w|-W [man options] page ...
```

***

## Sections of the man page

<table><thead><tr><th width="220">Section</th><th>Contents of the section</th></tr></thead><tbody><tr><td><code>1</code></td><td>User commands</td></tr><tr><td><code>2</code></td><td>Programming interfaces for kernel system calls</td></tr><tr><td><code>3</code></td><td>Programming interfaces to the C library</td></tr><tr><td><code>4</code></td><td>Special files such as device nodes and drivers</td></tr><tr><td><code>5</code></td><td>File formats</td></tr><tr><td><code>6</code></td><td>Games and amusements such as screen savers</td></tr><tr><td><code>7</code></td><td>Miscellaneous</td></tr><tr><td><code>8</code></td><td>System administration commands</td></tr></tbody></table>

## Important Flags

| Flag           | Description                                                  |
| -------------- | ------------------------------------------------------------ |
| `-f, –whatis`  | Display a concise one-line description of the command.       |
| `-k, –apropos` | Search for commands related to a given keyword.              |
| `-a, –all`     | Display all matching manual pages for the specified command. |
| `Spacebar`     | Move forward one page in the manual.                         |
| `Enter`        | Move forward one line in the manual.                         |
| `B`            | Move backward one page in the manual.                        |
| `Q`            | Quit the manual viewer.                                      |

***

## Examples

| Command                                                                                                                | Description                                                                                                                                                                                 |
| ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man [SECTION-NUM] [COMMAND NAME]
</code></pre> | In the man command manuals, sections are used to categorize different types of information. You can specify a section number to display only the relevant section of a manual.              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man -f [COMMAND NAME]
</code></pre>            | One may not be able to remember the sections in which a command is present. So this option gives the section in which the given command is present.                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man -a [COMMAND NAME]
</code></pre>            | This option helps us to display all the available intro manual pages in succession.                                                                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man -k [COMMAND NAME]
</code></pre>            | The -k option in the man command allows you to search for a command as a regular expression across all manual pages, returning a list of matching entries along with their section numbers. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man -w [COMMAND NAME]
</code></pre>            | The -w option in the man command returns the location of the manual page for a given command. This is useful for finding where the manual pages are stored on the system.                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man -I [COMMAND NAME]
</code></pre>            | The -I option in the man command makes the search case-sensitive, ensuring that the command name is considered with exact case.                                                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man cd
</code></pre>                           | To view the Manual for “cd” Command Using man Command                                                                                                                                       |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man -k file
</code></pre>                      | Searching for Commands Related to “file” Using man Command                                                                                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">man -f ls
</code></pre>                        | To Display a One-Line Description of “ls” Using man Command                                                                                                                                 |
