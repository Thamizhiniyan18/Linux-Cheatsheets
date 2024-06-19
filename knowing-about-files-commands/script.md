---
description: script linux command cheatsheet by Thamizhiniyan C S
---

# script

## Introduction

`script` command makes a typescript of everything on your terminal session. The terminal data are stored in raw form to the log file and information about timing to another (optional) structured log file.

***

## Syntax

`script [options] [file]`

***

## Important Flags

| Flag                   | Description                                     |
| ---------------------- | ----------------------------------------------- |
| `-I, --log-in`         | log stdin to file                               |
| `-O, --log-out`        | log stdout to file (default)                    |
| `-B, --log-io`         | log stdin and stdout to file                    |
| `-T, --log-timing`     | log timing information to file                  |
| `-t[], --timing[=]`    | deprecated alias to -T (default file is stderr) |
| `-m, --logging-format` | force to 'classic' or 'advanced' format         |
| `-a, --append`         | append to the log file                          |
| `-c, --command`        | run command rather than interactive shell       |
| `-e, --return`         | return exit code of the child process           |
| `-f, --flush`          | run flush after each write                      |
| `--force`              | use output file even when it is a link          |
| `-E, --echo`           | echo input in session (auto, always or never)   |
| `-o, --output-limit`   | terminate if output files exceed size           |
| `-q, --quiet`          | be quiet                                        |
| `-h, --help`           | display this help                               |
| `-V, --version`        | display version                                 |

***

## Examples

| Command                                                                                                                             | Description                                                                                                                                                                                        |
| ----------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script
</code></pre>                                        | To start a typescript without any argument. If no filename is given as argument, script will automatically create a file namely typescript in the home directory to save the recorded information. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script mysession.log
</code></pre>                          | This command starts a new recording session, with the output stored in the 'mysession.log' file.                                                                                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script $(date '+%d-%m-%Y')_session.log
</code></pre>        | This command records the terminal session and saves the output into a file with the current date as part of the name.                                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">exit
</code></pre>                                          | In order to stop the typescript, we just need to execute exit command and script will stop the capturing process.                                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script -a -f filename.txt
</code></pre>                     | To start the typescript, run any random command and save it in a text file, let’s say filename.txt.                                                                                                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script -c "cal"
</code></pre>                               | To get the typescript of cal command.                                                                                                                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script -c 'ls -la' directory_listing.log
</code></pre>      | This command runs 'ls -la' and records its output into 'directory\_listing.log' file.                                                                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script -c 'ls -la' | tee file.log
</code></pre>             | This command runs 'ls -la', displays its output and simultaneously saves it into 'file.log'.                                                                                                       |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script -f
</code></pre>                                     | This option is used to run flush output after each write.                                                                                                                                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script --force
</code></pre>                                | This option allows default output file i.e. typescript to be hard or symbolic link.                                                                                                                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script -h
</code></pre>                                     | Display this help and exit.                                                                                                                                                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script -q
</code></pre>                                     | This option does not display the notification stating that the script has started and quietly execute and exit the script command.                                                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script -t timing_file.txt
</code></pre>                     | This option allows user to capture the terminal activity step by step and appears like a video when the recorded file is executed with the help of scriptreplay command.                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">scriptreplay --timing=time_log geeksforgeeks1
</code></pre> | To replay the captured terminal activity.                                                                                                                                                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">script -V
</code></pre>                                     | Output version information and exit.                                                                                                                                                               |
