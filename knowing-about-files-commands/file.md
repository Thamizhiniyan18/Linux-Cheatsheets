---
description: file linux command cheatsheet by Thamizhiniyan C S
---

# file

## Introduction

The man command is used to determine the file type.

***

## Syntax

`file [-bcdEhiklLNnprsSvzZ0] [--apple] [--exclude-quiet] [--extension] [--mime-encoding] [--mime-type] [-e testname] [-F separator] [-f namefile] [-m magicfiles] [-P name=value] file ...`

`file -C [-m magicfiles]`

`file [--help]`

***

## Important Flags

| Flag                           | Description                                                                                                    |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------- |
| `--apple`                      | Changes the command output to the one used by older versions of MacOS.                                         |
| `-b, --brief`                  | Changes command output to brief mode.                                                                          |
| `-C, --compile`                | Creates an output file that contains a pre-parsed version of the magic file or directory.                      |
| `-c, --checking-printout`      | Checks the printout for the parsed version of the magic file.                                                  |
| `-d`                           | Prints internal debugging information in the standard error format.                                            |
| `-E`                           | On filesystem error, issues an error message and exits.                                                        |
| `-e, --exclude`                | Excludes a test from the list of tests performed on a file.                                                    |
| `--exclude-quiet`              | Excludes tests that the file command doesn't know about.                                                       |
| `--extension`                  | Prints a list of valid extensions for the file type.                                                           |
| `-F, --separator`              | Uses the provided string as a separator between the file name and file type.                                   |
| `-f, --files-from`             | Uses a provided text file as a list of files to test. The list must contain only one file name per line.       |
| `-h, --no-deference`           | Disables following symbolic links.                                                                             |
| `-i, --mime`                   | Changes the command output to a MIME-type string.                                                              |
| `--mime-type, --mime-encoding` | Changes the command output to a MIME-type string and only displays the specified element (type or encoding).   |
| `-k, --keep-going`             | Keeps the test going after the first results match.                                                            |
| `-l, --list`                   | Shows a list of matching patterns in descending order of strength.                                             |
| `-L, --deference`              | Enables following symbolic links.                                                                              |
| `-m, --magic-file`             | Uses an alternative magic file provided by the user.                                                           |
| `-N, --no-pad`                 | Doesn't pad the file names to align with the output.                                                           |
| `-n, --no-buffer`              | Flushes the output after checking each file.                                                                   |
| `-p, --preserve-date`          | Attempts to preserve the last time the file was accessed to make it look like the file command didn't test it. |
| `-P, --parameter`              | Sets various parameters, such as max bytes or recursion, count, and length limit.                              |
| `-r, --raw`                    | Disables translating unprintable characters.                                                                   |
| `-s, --special-files`          | Enables reading special files.                                                                                 |
| `-S, --no-sandbox`             | Disables sandboxing on systems that support it.                                                                |
| `-v, --version`                | Displays the version of the file command.                                                                      |
| `-z, --uncompress`             | Checks compressed files.                                                                                       |
| `-Z, --uncompress-noreport`    | Checks compressed files and only displays file type without the compression.                                   |
| `-0, --print0`                 | Displays a null character after the end of the file name.                                                      |
| `--help`                       | Displays the help message.                                                                                     |

***

## Examples

| Command                                                                                                                                   | Description                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file filename
</code></pre>                                       | To find the correct type of a file named 'filename'.                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file [file name 1] [file name 2] … [file name n]
</code></pre>    | Test multiple files simultaneously.                                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -b text.zip
</code></pre>                                    | View the file type in brief mode for a file named 'text.zip'.                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -b Example example.txt sample.png index.html
</code></pre>   | Display brief version of file type output.                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file *
</code></pre>                                              | List each file type in the current directory.                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file [path-to-directory]/*
</code></pre>                          | List each file type inside a specific directory.                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -i filename
</code></pre>                                    | View the MIME file type of a file named 'filename'.                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -z filename
</code></pre>                                    | Check detailed information and content of a compressed file like ZIP or gzip. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -z install.tar.gz
</code></pre>                              | Test a compressed file to detect its content.                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -Z filename
</code></pre>                                    | Display only the file type of a compressed file like ZIP or gzip.             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -c filename
</code></pre>                                    | View the parsed version of a file, useful for debugging magic files.          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -c example.txt
</code></pre>                                 | Display the check printout for the parsed version of a file.                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file [range1-range2]*
</code></pre>                               | List all file types within specified Regex-style ranges.                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file [a-l]*
</code></pre>                                         | Test files in a directory within the range of names from 'a' to 'l'.          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file [a-z]* [A-Z]*
</code></pre>                                  | List all file types within specified Regex-style ranges.                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -f list.txt
</code></pre>                                    | Test files listed in a text file (one file per line).                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file /dev/sda5
</code></pre>                                      | Test a special system file.                                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sudo file -s /dev/sda5
</code></pre>                              | Fully test a special system file (requires root).                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -F + Example example.txt sample.png index.html
</code></pre> | Define '+' as a separator between file name and type in output.               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">file -N Example example.txt sample.png index.html
</code></pre>   | Remove padding between file name and type in output.                          |
