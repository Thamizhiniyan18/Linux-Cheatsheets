---
description: alias linux command cheatsheet by Thamizhiniyan C S
---

# alias

## Introduction

The **`alias`** command allows the user to create replacements for other commands and make them easier to remember and use.

***

## Syntax

`alias [option] [alias]='[command-or-path]'`

***

## Important Flags

| Flag | Description                                     |
| ---- | ----------------------------------------------- |
| `-p` | Print the list of currently defined aliases.    |
| `-a` | Define alias for all users (must be superuser). |

***

## Examples

<table><thead><tr><th width="252">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">alias
</code></pre></td><td>To list all available aliases on the system</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">alias -p
</code></pre></td><td>To list all available aliases on the system (Same as the above command)</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">alias print="echo"
</code></pre></td><td>Creating an alias named `print` which executes the `echo` command</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">alias list='ls -la'
</code></pre></td><td>Creating an alias named `list` which executes the `ls -la` command</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">unalias [alias]
</code></pre></td><td>To remove an alias</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">unalias -a
</code></pre></td><td>To remove all alias</td></tr></tbody></table>
