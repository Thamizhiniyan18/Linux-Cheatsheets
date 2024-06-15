# df

## Introduction

The df command is used to check the file system space usage.

***

## Syntax

`df [OPTION]... [FILE]...`

***

## Important Flags

| Flag                     | Description                                                                                  |
| ------------------------ | -------------------------------------------------------------------------------------------- |
| `-a or --all`            | Includes pseudo, duplicate, and inaccessible file systems in the output.                     |
| `-B or --block-size=`    | Scales sizes by SIZE before printing them.                                                   |
| `-H or --si`             | Prints sizes in a human-readable format using power of 1000.                                 |
| `-h or --human-readable` | Prints sizes in a human-readable format. Print sizes in powers of 1024 (e.g., 1023M)         |
| `--help`                 | Display this help and exit.                                                                  |
| `--inodes`               | Lists inode information instead of block usage.                                              |
| `-l or --local`          | Limits listing to local file systems.                                                        |
| `--no-sync`              | Do not invoke sync before getting usage info (default).                                      |
| `--output[=FIELD_LIST]`  | Use the output format defined by FIELD\_LIST, or print all fields if FIELD\_LIST is omitted. |
| `-P or --portability`    | Use the POSIX output format.                                                                 |
| `-T,--print-type`        | Prints file system type.                                                                     |
| `-s, --summarize`        | Get a summary of the directory's usage in a human-readable format.                           |
| `--sync`                 | Invoke sync before getting usage info.                                                       |
| `--time`                 | Show the time of the last modification to any file in the directory or subdirectory.         |
| `-t, --type=TYPE`        | Limit listing to file systems of type TYPE.                                                  |
| `-v`                     | (Ignored).                                                                                   |
| `--version`              | Output version information and exit.                                                         |

***

## Examples

| Command                                                                                                                        | Description                                                      |
| ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df
</code></pre>                                       | Check disk usage on all mounted filesystems.                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df .
</code></pre>                                     | Display available space on the current file system.              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -h
</code></pre>                                    | Check disk usage in a human-readable format.                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -h --total
</code></pre>                            | Show total available disk space.                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -h --total|grep ^total
</code></pre>                | Show only the total available disk space.                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -h /
</code></pre>                                  | Check disk space available on the root mount point.              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -h /boot
</code></pre>                              | Check disk space available on the /boot mount point.             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -h --output=source,avail,pcent,target
</code></pre> | Customize the output to show only specific fields.               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -i
</code></pre>                                    | Show inode usage on each mounted filesystem.                     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -k /test
</code></pre>                              | Display information about /test file system in 1024-byte blocks. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -m /test
</code></pre>                              | Display information about /test file system in MB blocks.        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">df -T
</code></pre>                                    | Display information about all locally file systems.              |
