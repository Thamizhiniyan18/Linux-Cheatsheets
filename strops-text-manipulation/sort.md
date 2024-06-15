---
description: sort linux command cheatsheet by Thamizhiniyan C S
---

# sort

## Introduction

sort command, as the name suggests sorts the lines alphabetically and numerically, automatically.

***

## Syntax

`sort [OPTION]... [FILE]...`

***

## Important Flags

| Flags         | Description                                                                                                            |
| ------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `-r`          | Sorts in reverse order                                                                                                 |
| `-c`          | This flag is used to check whether the file is already sorted or not(If not, it will list, where the disorder started) |
| `-u`          | To sort and removes duplicate lines(does work same as stdin redirected into `uniq`)                                    |
| `-o save.txt` | To save into a output file                                                                                             |
| `-t`          | Define Field Separator                                                                                                 |
| `-k`          | Reorders data in a specific field                                                                                      |
| `-n`          | Sorts the file numerically                                                                                             |
| `-M`          | Sorts by month names                                                                                                   |

***

## Examples

<table><thead><tr><th width="383">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash"><code class="lang-bash">sort -d
</code></pre></td><td>Order the lines in lexicographical order</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sort -r
</code></pre></td><td>Order the lines in reverse lexicographical order (i.e. <em>Z-A</em> instead of <em>A-Z</em>)</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sort -n
</code></pre></td><td>Sort the lines in ascending order based on numbers</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sort -n -r
</code></pre></td><td>Sort the lines in descending order based on numbers</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sort -t $'\t' -k 2 -n -r
</code></pre></td><td>Sorts lines of text based on the second field (using a numerical comparison) in reverse order, considering tab characters as the field separator</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sort -t $'\t' -k 2 -n
</code></pre></td><td>Sort lines of text based on the second field in ascending numerical order, considering tab characters as the field separator</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sort -t '|' -k 2 -n -r
</code></pre></td><td>Sort lines of text based on the second field in descending numerical order, considering '|' as the field separator.</td></tr></tbody></table>
