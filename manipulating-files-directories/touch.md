---
description: touch linux command cheatsheet by Thamizhiniyan C S
---

# touch

## Introduction

The primary function of the `touch` command is to modify a file's timestamp. While it is often used to create files, this is not its main purpose.

***

## Syntax

`touch [OPTION]... FILE...`

***

## Important Flags

| Flag                   | Description                                                                                                                   |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `-a`                   | change only the access time                                                                                                   |
| `-c, --no-create`      | do not create any files                                                                                                       |
| `-d, --date=STRING`    | parse STRING and use it instead of current time                                                                               |
| `-f`                   | (ignored)                                                                                                                     |
| `-h, --no-dereference` | affect each symbolic link instead of any referenced file (useful only on systems that can change the timestamps of a symlink) |
| `-m`                   | change only the modification time                                                                                             |
| `-r, --reference=FILE` | use this file's times instead of current time                                                                                 |
| `-t STAMP`             | use \[\[CC]YY]MMDDhhmm\[.ss] instead of current time                                                                          |
| `--time=WORD`          | change the specified time: WORD is access, atime, or use: equivalent to -a: WORD is modify or mtime: equivalent to -m         |
| `--help`               | display this help and exit                                                                                                    |
| `--version`            | output version information and exit                                                                                           |

***

## Time Stamp Formats

Syntax: `[[CC]YY]MMDDhhmm[.ss]`

| Format | Description                     |
| ------ | ------------------------------- |
| `CC`   | the first two digits for a year |
| `YY`   | the last two digits for a year  |
| `MM`   | the month                       |
| `DD`   | the day                         |
| `hh`   | the hour                        |
| `mm`   | the minutes                     |
| `ss`   | the seconds                     |

***

## Examples

| Command                                                                                                                         | Description                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch filename
</code></pre>                            | To create a emtpy file                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch File1_name File2_name File3_name
</code></pre>    | To create multiple files at the same time. These files will be empty upon creation. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch test{1..10}
</code></pre>                         | To create ten files with appended numbering                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch test_{a..j}
</code></pre>                         | To create ten files with appended alphabets                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -a [filename]
</code></pre>                       | To change a file's access time to the current timestamp.                            |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -at [timestamp] [filename]
</code></pre>          | To modify access time explicitly.                                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -am [filename]
</code></pre>                      | To change both modification and access times to the current timestamp.              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -c fileName
</code></pre>                         | Checks if a file is created; if not, it doesn’t create it.                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -c -d fileName
</code></pre>                      | Updates both access and modification times.                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -m [filename]
</code></pre>                       | To change a file's modification time to the current timestamp.                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -mt [timestamp] [filename]
</code></pre>          | To set modification time explicitly.                                                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -d "17 Mar 2023" fileName
</code></pre>           | Changes the modification date only.                                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -r [reference file] [file]
</code></pre>          | To set a file's timestamp based on another file's timestamp.                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -r second_file_name first_file_name
</code></pre> | Uses the timestamp of another file.                                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -t YYMMDDHHMM fileName
</code></pre>              | Creates a file with a specified time.                                               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -t [timestamp] [existing_filename]
</code></pre>  | To set a specific timestamp for an existing file.                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">touch -h [filename]
</code></pre>                       | To modify the timestamp of a symbolic link without affecting the referenced file.   |
