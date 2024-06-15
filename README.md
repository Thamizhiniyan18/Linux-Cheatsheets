---
description: id linux command cheatsheet by Thamizhiniyan C S
---

# id

## Introduction

The id command is used to print real and effective user and group IDs

***

## Syntax

`id [OPTION]... [USER]...`

***

## Important Flags

| Flag       | Description                               |
| ---------- | ----------------------------------------- |
| `-g`       | Print only the effective group id.        |
| `-G`       | Print all Group ID’s.                     |
| `-n`       | Prints name instead of number.            |
| `-r`       | Prints real ID instead of numbers.        |
| `-u`       | Prints only the effective user ID.        |
| `–help`    | Display help messages and exit.           |
| `–version` | Display the version information and exit. |

***

## Examples

<table><thead><tr><th width="227">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id
</code></pre></td><td>Print the current user's UID and GID.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id -u root
</code></pre></td><td>Find the UID of the user named "root".</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id -g root
</code></pre></td><td>Find the GID of the user named "root".</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id root
</code></pre></td><td>Find the UID and all groups associated with the user "root".</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id -G root
</code></pre></td><td>Display the UID and all groups a user "root" belongs to.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id -ng root
</code></pre></td><td>Display the name instead of numbers for GID of "root".</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id -nu root
</code></pre></td><td>Display the name instead of numbers for UID of "root".</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id -nG root
</code></pre></td><td>Display the name instead of numbers for all groups of "root".</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id -r -g root
</code></pre></td><td>Display the real GID instead of effective GID of "root".</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id -r -u root
</code></pre></td><td>Display the real UID instead of effective UID of "root".</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">id -r -G root
</code></pre></td><td>Display the real group IDs instead of effective groups of "root".</td></tr></tbody></table>
