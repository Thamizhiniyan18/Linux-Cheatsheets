---
description: du linux command cheatsheet by Thamizhiniyan C S
---

# du

## Introduction

`du` is a command in linux (short for disk usage) which helps you identify what files/directories are consuming how much space.

***

## Syntax

`du [OPTION]... [FILE]...`

`du [OPTION]... --files0-from=F`

***

## Important Flags

<table><thead><tr><th width="291">Flag</th><th>Description</th></tr></thead><tbody><tr><td><code>-0, --null</code></td><td>End each output line with NULL</td></tr><tr><td><code>-a or --all</code></td><td>Displays disk usage information for all files and directories, including hidden ones.</td></tr><tr><td><code>--apparent-size</code></td><td>Print apparent sizes, rather than disk usage</td></tr><tr><td><code>-B, --block-size=SIZE</code></td><td>Scale sizes to SIZE before printing on console</td></tr><tr><td><code>-c or --total</code></td><td>Shows the total disk usage in addition to individual usage for directories and files.</td></tr><tr><td><code>-d, --max-depth=N</code></td><td>Print total for directory only if it is N or fewer levels below command line argument</td></tr><tr><td><code>-h or --human-readable</code></td><td>Displays sizes in human-readable format, using units such as KB, MB, GB, etc. This option makes it easier to interpret the disk usage information.</td></tr><tr><td><code>-S, -separate-dirs</code></td><td>For directories, don’t include size of subdirectories</td></tr><tr><td><code>-s or --summarize</code></td><td>Provides a summary of the disk usage for the specified directory or file, without displaying individual usage details for subdirectories.</td></tr><tr><td><code>--time</code></td><td>Show time of last modification of any file or directory</td></tr><tr><td><code>--exclude</code></td><td>Excludes specific directories or files from disk usage calculation based on patterns or names.</td></tr></tbody></table>

***

## Examples

| Command                                                                                                                                           | Description                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -a /home
</code></pre>                                                 | To display the disk usage information for all files and directories, including hidden ones in the home directory.                                                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -h /home
</code></pre>                                                 | You can print sizes in human-readable format (e.g., 1K 234M 2G), using the \`-h\` option.                                                                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -a -h /home
</code></pre>                                              | Combine \`-a\` and \`-h\` flags together to check all files and folder sizes.                                                                                                                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -c -h /home
</code></pre>                                              | Use -c option to print total size                                                                                                                                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -d 1 /home
</code></pre>                                               | To print sizes to particular level, use -d option with level no.                                                                                                                                       |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -d 2 /home
</code></pre>                                               | Now try with level 2, you will get some extra directories                                                                                                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -s /home
</code></pre>                                                 | Get summary of file system using -s option                                                                                                                                                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -sh --apparent-size /home
</code></pre>                                | Print apparent sizes, rather than disk usage; although the apparent size is usually smaller, it may be larger due to holes in (‘sparse’) files, internal fragmentation, indirect blocks, and the like. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du --time -h /home
</code></pre>                                          | Get the timestamp of last modified using --time option                                                                                                                                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du --time -d 1 /home/
</code></pre>                                       | Check the timestamp of the last modification of files and directories to 1 level.                                                                                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du --max-depth=1 /path
</code></pre>                                      | To find the largest directories, you can use the du command with the --max-depth option.                                                                                                               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -h /path
</code></pre>                                                 | The du command supports the -h option to display sizes in a human-readable format (e.g., KB, MB, GB).                                                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find /path -type f -exec du -h {} + | sort -rh | head -n 10
</code></pre> | You can combine the find command with du to identify large files.                                                                                                                                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">du -h --exclude=/path/to/exclude /path
</code></pre>                      | To exclude specific directories, use the --exclude option with the du command.                                                                                                                         |
