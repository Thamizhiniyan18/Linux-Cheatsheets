---
description: who linux command cheatsheet by Thamizhiniyan C S
---

# who

## Introduction

This command is used to show who is logged on.

***

## Syntax

`who [OPTION]... [ FILE | ARG1 ARG2 ]`

***

## Important Flags

<table><thead><tr><th width="229">Flag</th><th>Description</th></tr></thead><tbody><tr><td><code>-a, --all</code></td><td>Print all information provided by -b, -d, --login, -p, -r, -t, -T, -u options.</td></tr><tr><td><code>-b, --boot</code></td><td>Display the time of the last system boot.</td></tr><tr><td><code>-d, --dead</code></td><td>Print dead processes.</td></tr><tr><td><code>-H, --heading</code></td><td>Print a line of column headings.</td></tr><tr><td><code>--ips</code></td><td>Print IPs instead of hostnames. With --lookup, canonicalizes based on stored IP, if available, rather than stored hostname.</td></tr><tr><td><code>-l, --login</code></td><td>Print system login processes.</td></tr><tr><td><code>--lookup</code></td><td>Attempt to canonicalize hostnames via DNS.</td></tr><tr><td><code>-m</code></td><td>Display only hostname and user associated with stdin.</td></tr><tr><td><code>-p, --process</code></td><td>Print active processes spawned by init.</td></tr><tr><td><code>-q, --count</code></td><td>Print all login names and the number of users logged on.</td></tr><tr><td><code>-r, --runlevel</code></td><td>Print the current runlevel.</td></tr><tr><td><code>-s, --short</code></td><td>Print only name, line, and time (default).</td></tr><tr><td><code>-t, --time</code></td><td>Print the last system clock change.</td></tr><tr><td><code>-T, -w, --mesg</code></td><td>Add user's message status as +, - or ?.</td></tr><tr><td><code>-u, --users</code></td><td>List users logged in.</td></tr><tr><td><code>--message</code></td><td>Same as -T.</td></tr><tr><td><code>--writable</code></td><td>Same as -T.</td></tr><tr><td><code>--help</code></td><td>Display help information and exit.</td></tr><tr><td><code>--version</code></td><td>Output version information and exit.</td></tr></tbody></table>

***

## Examples

<table><thead><tr><th width="195">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who
</code></pre></td><td>Display a list of the logged-in usernames.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -s
</code></pre></td><td>Achieve the same effect as 'who' with the short format.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -H
</code></pre></td><td>Print column headers above the list of users.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -m
</code></pre></td><td>Display information about the current user only.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -l
</code></pre></td><td>Show a list of available terminals.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -b
</code></pre></td><td>Display the time of the last system boot.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -q
</code></pre></td><td>List the usernames and the number of users currently logged on.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -T
</code></pre></td><td>Show the user's message status.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -p
</code></pre></td><td>Print a list of active processes spawned by init.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -d
</code></pre></td><td>Print a list of dead processes.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -r
</code></pre></td><td>Display the current runlevel of the system.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -t
</code></pre></td><td>Print the last time the system clock was changed.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -u
</code></pre></td><td>Show how long each user has been idle.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">who -a
</code></pre></td><td>Print all information provided by various options in a single output.</td></tr></tbody></table>
