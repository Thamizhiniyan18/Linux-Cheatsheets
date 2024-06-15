---
description: nl linux command cheatsheet by Thamizhiniyan C S
---

# nl

## Introduction

The nl command is used to number lines of files.

***

## Syntax

`nl [OPTION]... [FILE]...`

***

## Important Flags

<table><thead><tr><th width="301">Flags</th><th>Description</th></tr></thead><tbody><tr><td><code>-b STYLE</code> </td><td>Used for numbering body lines</td></tr><tr><td><code>-i NUMBER</code></td><td>Line number increment at each line</td></tr><tr><td><code>-n FORMAT</code></td><td>Insert line numbers according to FORMAT</td></tr><tr><td><code>-v NUMBER</code></td><td>Change first line number of the given input</td></tr><tr><td><code>-l NUMBER</code></td><td>Group of NUMBER empty lines are counted as one</td></tr><tr><td><code>-s STRING</code></td><td>Add any STRING after every logical line number</td></tr><tr><td><code>-w NUMBER</code></td><td>Use different NUMBER columns for line numbers</td></tr></tbody></table>

### Default Options

`-b t -d ':' -f n -h n -i 1 -l 1 -n 'rn' -s -v 1 -w 6`

### STYLE to be used with Options

| Values | Description                                                                  |
| ------ | ---------------------------------------------------------------------------- |
| `a`    | Number all lines                                                             |
| `t`    | Number only nonempty lines                                                   |
| `n`    | Number no lines                                                              |
| `pBRE` | Number only lines that contain a match for the basic regular expression, BRE |

### FORMAT to be used with Options

| Flags | Description                       |
| ----- | --------------------------------- |
| `ln`  | Left justified, no leading zeros  |
| `rn`  | Right justified, no leading zeros |
| `rz`  | Right justified, leading zeros    |

***

## Examples

| Command                                                                                                      | Description                                                                                       |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl readme.md
</code></pre>           | To display a file with line numbers (Numbers all non-empty lines)                                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -b a readme.md
</code></pre>      | To number all lines (including empty lines also)                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -b a -l 3 readme.md
</code></pre> | Count multiple, consecutive, non-empty lines as one                                               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -i 3 readme.md
</code></pre>      | Override default increment                                                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -v 4 readme.md
</code></pre>      | To make the starting line number different                                                        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -s "..." readme.md
</code></pre>  | Add a string literal after line numbers                                                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -w 6 readme.md
</code></pre>      | Change column for line numbers                                                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -b pF readme.md
</code></pre>     | To number all logical lines that match the specified REGEX (number those lines that begin with F) |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -n ln readme.md
</code></pre>     | To print the lines using left-justified, no leading zeros number format                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -n rn readme.md
</code></pre>     | To print the lines using right-justified, no leading zeros number format                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">nl -n rz readme.md
</code></pre>     | To print the lines using right-justified with leading zeros format                                |
