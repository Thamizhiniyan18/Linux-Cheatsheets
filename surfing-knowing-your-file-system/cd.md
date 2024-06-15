---
description: cd linux command cheatsheet by Thamizhiniyan C S
---

# cd

## Introduction

This command is used to change the current working directory.

***

## Syntax

`cd [-L|[-P [-e]] [-@]] [dir]`

***

## Important Flags

| Flag | Description                                                                               |
| ---- | ----------------------------------------------------------------------------------------- |
| `-L` | Force symbolic links to be followed.                                                      |
| `-P` | Use the physical directory structure without following symbolic links.                    |
| `-e` | Exit with a non-zero status if the current directory can't be determined (when using -P). |
| `-@` | Show a file with extended attributes as a directory containing the attributes.            |

> The default behaviour of the `cd` command is to follow symbolic links, as if `-L' were specified.` ..' is processed by removing the immediately previous pathname component back to a slash or the beginning of DIR.

***

## Examples

| Command                                                                                                                       | Description                                                                                     |
| ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd [directory_name]
</code></pre>                     | Move inside a subdirectory in Linux. Replace \`\[directory\_name]\` with the desired directory. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd /
</code></pre>                                    | Change the directory to the root directory using \`/\` as an argument.                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd ~
</code></pre>                                    | Change the directory to the home directory from any location in the Linux System.               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd
</code></pre>                                      | Change back to the default working directory. No arguments needed.                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd ..
</code></pre>                                   | Move to the parent directory or one level up from the current directory.                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd [path to directory] &#x26;&#x26; ls
</code></pre>  | Change to a new directory and list its contents simultaneously.                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd [path to directory]
</code></pre>                  | Change to a new working directory.                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd -
</code></pre>                                    | Return to the previous working directory.                                                       |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd ~[username]
</code></pre>                          | Change to another user's Home directory.                                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd 'Directory name with blank spaces'
</code></pre>   | Change to a directory with spaces in the name using single quotation marks.                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cd Directory\ name\ with\ blank\ spaces
</code></pre> | Change to a directory with spaces in the name using backslashes.                                |
