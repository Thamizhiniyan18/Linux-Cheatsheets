---
description: xargs linux command cheatsheet by Thamizhiniyan C S
---

# xargs

## Introduction

`xargs` is a command line tool used to build and execute command from the standard input.

***

## Syntax

{% code overflow="wrap" %}
```bash
xargs [-p t x ] [-e [EOFString]] [-E EOFString] [-i [ReplaceString] ] [-I ReplaceString | -L Number | -n Number] [ -l [ Number]] [-s Size] [Command [Argument ... ]]
```
{% endcode %}

***

## Important Flags

| Flags          | Description                                                                                                                                                                                                                                                                                          |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-0`           | Will terminate the arguments with null character (helps to handle spaces in the argument)                                                                                                                                                                                                            |
| `-a file`      | This option allows xargs to read item from a file                                                                                                                                                                                                                                                    |
| `-d delimiter` | To specify the delimiter to be used when differentiating arguments in stdin                                                                                                                                                                                                                          |
| `-L int`       | Specifies max number non-blank inputs per command line                                                                                                                                                                                                                                               |
| `-s int`       | Consider this as a buffer size that you allocate while running xargs, it sets the max-chars for the command, which includes it's initial arguments and terminating nulls as well.(You won't be using this most of the times but it's good to know). Default size is around 128kB (if not specified). |
| `-x`           | This flag will exit the command execution if the size specified is exceeded.(For security purposes.)                                                                                                                                                                                                 |
| `-E str`       | This is to specify the end-of-file string (You can use this in case you are reading arguments from a file)                                                                                                                                                                                           |
| `-I str`       | (Capital i) Used to replace str occurrence in arguments with the one passed via stdin(More like creating a variable to use later)                                                                                                                                                                    |
| `-p`           | prompt the user before running any command as a token of confirmation.                                                                                                                                                                                                                               |
| `-r`           | If the standard input is blank (i.e. no arguments passed) then it won't run the command.                                                                                                                                                                                                             |
| `-n int`       | This specifies the limit of max-args to be taken from command input at once. After the max-args limit is reached, it will pass the rest arguments into a new command line with the same flags issued to the previously ran command. (More like a looping)                                            |
| `-t`           | verbose; (Print the command before running it).Note: This won't ask for a prompt                                                                                                                                                                                                                     |

***

## Examples

| Command                                                                                                                                                                    | Description                                                                                                 |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">echo 'file1 file2 file3' | xargs -t -I argVar sh -c '{ touch argVar; ls -l argVar;}'
</code></pre> | To run multiple commands in one line                                                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find ./ -type f -print0 | xargs -0 -t -p rm -f
</code></pre>                                       | To find and delete files with a prompt                                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find ./ -type f -print0 | xargs -0 egrep '^r\w*0$'
</code></pre>                                   | Looking out for files with the given pattern of words                                                       |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat file | xargs -I files -t sh -c "touch files; chmod 664 files"
</code></pre>                    | To create files and change its permission to read-only to the owner                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">ls | xargs -I word -n 1 -t sh -c "echo word >> shortrockyou; rm word"
</code></pre>                | To list the directory, append all the names of the files in the directory to a file and remove those files. |
