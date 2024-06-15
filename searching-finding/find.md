---
description: find linux command cheatsheet by Thamizhiniyan C S
---

# find

## Introduction

The find command is used to search for files in a directory hierarchy.

***

## Syntax

`find [-H] [-L] [-P] [-D debugopts] [-Olevel] [starting-point...] [expression]`

***

## Important Flags

<table><thead><tr><th width="289">Flag</th><th>Description</th></tr></thead><tbody><tr><td><code>-H</code></td><td>Follow symbolic links on command line only.</td></tr><tr><td><code>-L</code></td><td>Follow all symbolic links.</td></tr><tr><td><code>-P</code></td><td>Never follow symbolic links.</td></tr><tr><td><code>-D</code></td><td>Process debugging option.</td></tr><tr><td><code>-name</code></td><td>Matches files/directories by name.</td></tr><tr><td><code>-type</code></td><td>Matches files by type.</td></tr><tr><td><code>-perm</code></td><td>Matches files by permission.</td></tr><tr><td><code>-user</code></td><td>Matches files by owner.</td></tr><tr><td><code>-mtime</code></td><td>Matches files by modification time.</td></tr><tr><td><code>-atime</code></td><td>Matches files by access time.</td></tr><tr><td><code>-cmin</code></td><td>Matches files by changed minutes ago.</td></tr><tr><td><code>-amin</code></td><td>Matches files by accessed minutes ago.</td></tr><tr><td><code>-size</code></td><td>Matches files by size.</td></tr><tr><td><code>-writable</code></td><td>Matches files that are writable.</td></tr></tbody></table>

***

## Examples

<table><thead><tr><th width="427">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash"><code class="lang-bash">man find
</code></pre></td><td>Read the manual for the find command</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find . -name flag1.txt
</code></pre></td><td>find the file named “flag1.txt” in the current directory</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find /home -name flag1.txt
</code></pre></td><td>find the file names “flag1.txt” in the /home directory</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find / -type d -name config
</code></pre></td><td>find the directory named config under “/”</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find / -type f -perm 0777
</code></pre></td><td>find files with the 777 permissions (files readable, writable, and executable by all users)</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find / -perm a=x
</code></pre></td><td>find executable files</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find /home -user frank
</code></pre></td><td>find all files for user “frank” under “/home”</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -mtime 10
</code></pre></td><td>find files that were modified in the last 10 days</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -atime 10
</code></pre></td><td>find files that were accessed in the last 10 day</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -cmin -60
</code></pre></td><td>find files changed within the last hour (60 minutes)</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -amin -60
</code></pre></td><td>find files accesses within the last hour (60 minutes)</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -size 50M
</code></pre></td><td>find files with a 50 MB size</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -size +100M
</code></pre></td><td>find files that are larger than 100 MB</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -size +100M -type f 2>/dev/null
</code></pre></td><td>redirect errors to “/dev/null” and have a cleaner output</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -writable -type d 2>/dev/null
</code></pre></td><td>Find world-writeable folders</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -perm -222 -type d 2>/dev/null
</code></pre></td><td>Find world-writeable folders</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -perm -o w -type d 2>/dev/null
</code></pre></td><td>Find world-writeable folders</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -perm -o x -type d 2>/dev/null
</code></pre></td><td>Find world-executable folders</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -name perl*
</code></pre></td><td>Find files/directories named "gcc*"</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -name python*
</code></pre></td><td>Find files with setuid, suppress errors</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -name gcc*
</code></pre></td><td>Find setuid files, suppress errors</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -perm -u=s -type f 2>/dev/null
</code></pre></td><td>Find files with the SUID bit</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">find / -perm -4000 2>/dev/null
</code></pre></td><td>Find files with the SUID bit</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find [directory path] -type f -newerat [start date range] ! -newerat [end date range]
</code></pre></td><td>Find files based on date accessed</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find [directory path] -type f -newermt [start date range] ! -newermt [end date range]
</code></pre></td><td>Find files based on date modified</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find [directory path] -type f -newermt '[date and time]'
</code></pre></td><td>Find files modified after a specific date</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find [directory path] -type f -group [group name]
</code></pre></td><td>Find files based on group name</td></tr></tbody></table>

