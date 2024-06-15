---
description: w linux command cheatsheet by Thamizhiniyan C S
---

# w

## Introduction

This command is used to show who is logged on and what they are doing.

***

## Syntax

`w [options] [user]`

Using the **`w`** command without any additional options produces an output similar to this:

<figure><img src="https://phoenixnap.com/kb/wp-content/uploads/2021/08/w-command-linux-01-output-breakdown.png" alt="Elements of the w command output" height="354" width="800"><figcaption><p>Source: <a href="https://phoenixnap.com/kb/w-command-in-linux">https://phoenixnap.com/kb/w-command-in-linux</a></p></figcaption></figure>

The first line of the output shows system information:

* **System time:** The current system time.
* **Up time:** How long the system has logged in.
* **Number of users:** The number of users currently logged in.
* **Average system load:** The average number of jobs running on the system in the last 1, 5, and 15 minutes, respectively.

The second line shows user and process information:

* **`USER`:** The names of currently logged in users.
* **`TTY`:** The name of the terminal the user is logging in from.
* **`FROM`:** The name or [IP address](https://phoenixnap.com/kb/how-to-find-ip-address-linux) of the terminal or host the user is logging in from.
* **`LOGIN@`:** The time the user logged in, in a 24-hour format.
* **`IDLE`:** The time since the user last used the terminal; displays **?xdm?** if the user is currently active.
* **`JCPU`:** The total run time of all [system processes](https://phoenixnap.com/kb/how-to-kill-a-process-in-linux) attached to the user's terminal.
* **`PCPU`:** Elapsed time for the user's current process.
* **`WHAT`:** The name of the user's current process.

***

## Important Flags

| Flag               | Description                                                                |
| ------------------ | -------------------------------------------------------------------------- |
| `-h, --no-header`  | Print output without the header.                                           |
| `-u, --no-current` | Ignore username when calculating current process times and load.           |
| `-s, --short`      | Print output in the short format.                                          |
| `-f, --from`       | Toggle printing the FROM (remote hostname) field.                          |
| `--help`           | Display help text.                                                         |
| `-i, --ip-addr`    | Replace the hostname in the FROM field with the IP address.                |
| `-V, --version`    | Display current command version.                                           |
| `-o, --old-style`  | Print old-style output (blank space for idle times shorter than 1 minute). |

***

## Examples

<table><thead><tr><th width="268">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">w -s
</code></pre></td><td>Display the short format version of the w command output.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">w -h
</code></pre></td><td>List the w command output without printing the header.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">w -u
</code></pre></td><td>Ignore usernames when calculating current process and CPU times.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">w -V
</code></pre></td><td>Check the current version of the w command.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">w -i
</code></pre></td><td>Display the user's IP address in the FROM field.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">w -o
</code></pre></td><td>Display the output in the old style, leaving blank spaces for short idle times.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">w -f
</code></pre></td><td>Toggle the FROM field in the w command output.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">w [username]
</code></pre></td><td>Display the w command output for a specific user.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">w --help
</code></pre></td><td>Display all the available options for the w command.</td></tr></tbody></table>
