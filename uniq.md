---
description: uniq linux command cheatsheet by Thamizhiniyan C S
---

# uniq

## Introduction

Unique command filters the output (from either a file or stdin) to remove any duplicates.

***

## Syntax

`uniq [OPTION]... [INPUT [OUTPUT]]`

***

## Important Flags

| Flags | Description                                                               |
| ----- | ------------------------------------------------------------------------- |
| `-c`  | To count the occurrences of every line in file or stdin                   |
| `-d`  | Will only print the lines that are repeated, not the one which are unique |
| `-u`  | Will only print lines that are already uniq                               |
| `-i`  | Ignores case(Default is case-sensitive)                                   |

***

## Examples

<table><thead><tr><th width="381">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash"><code class="lang-bash">uniq
</code></pre></td><td>Remove the consecutive repetitions of any line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">uniq -c | cut -c 7-
</code></pre></td><td>Count the occurrences of consecutive identical lines in the input, then cut out the first six characters (presumably to remove the counts added by <code>uniq -c</code>), leaving only the original content of the lines</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">uniq -c -i | cut -c 7-
</code></pre></td><td>Count the occurrences of consecutive identical lines while ignoring case differences and then remove the count information, leaving only the original content of the lines</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">uniq -u
</code></pre></td><td>Print only the lines that occur exactly once in the input, discarding any duplicate lines.</td></tr></tbody></table>
