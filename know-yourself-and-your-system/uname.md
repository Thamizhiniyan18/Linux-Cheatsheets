---
description: uname linux command cheatsheet by Thamizhiniyan C S
---

# uname

## Introduction

This command is used to print system information.

***

## Syntax

`uname [OPTION]...`

***

## Important Flags

| Flags                     | Description                                                                     |
| ------------------------- | ------------------------------------------------------------------------------- |
| `-a, --all`               | print all information, in the following order, except omit -p and -i if unknown |
| `-s, --kernel-name`       | print the kernel name                                                           |
| `-n, --nodename`          | print the network node hostname                                                 |
| `-r, --kernel-release`    | print the kernel release                                                        |
| `-v, --kernel-version`    | print the kernel version                                                        |
| `-m, --machine`           | print the machine hardware name                                                 |
| `-p, --processor`         | print the processor type (non-portable)                                         |
| `-i, --hardware-platform` | print the hardware platform (non-portable)                                      |
| `-o, --operating-system`  | print the operating system                                                      |

***

## Examples

| Command                                                                                        | Description                               |
| ---------------------------------------------------------------------------------------------- | ----------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">uname -a
</code></pre> | Prints all system information.            |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">uname -s
</code></pre> | Prints the kernel name.                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">uname -n
</code></pre> | Prints the hostname of the network node.  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">uname -r
</code></pre> | Prints the kernel release date.           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">uname -v
</code></pre> | Prints the version of the current kernel. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">uname -m
</code></pre> | Prints the machine hardware name.         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">uname -p
</code></pre> | Prints the type of processor.             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">uname -i
</code></pre> | Prints the platform of the hardware.      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">uname -o
</code></pre> | Prints the name of the operating system.  |
