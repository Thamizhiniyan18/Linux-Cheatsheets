---
description: tr linux command cheatsheet by Thamizhiniyan C S
---

# tr

## Introduction

Translate command(`tr`) can help you in number of ways, ranging from changing character cases in a string to replacing characters in a string.

***

## Syntax

`tr [flags] [source]/[find]/[select] [destination]/[replace]/[change]`

***

## Important Flags

<table><thead><tr><th width="153">Flags</th><th>Description</th></tr></thead><tbody><tr><td><code>-d</code></td><td>To delete a given set of characters</td></tr><tr><td><code>-t</code></td><td>To concat source set with destination set(destination set comes first; t stands for truncate)</td></tr><tr><td><code>-s</code></td><td>To replace the source set with the destination set(s stands for squeeze)</td></tr><tr><td><code>-c</code></td><td>This is the REVERSE card in this game, for eg. If you specify -c with -d to delete a set of characters then it will delete the rest of the characters leaving the source set which we specified (c stands for complement; as in doing reverse of something)</td></tr><tr><td><code>[:alnum:]</code></td><td>all letters and digits</td></tr><tr><td><code>[:alpha:]</code></td><td>all letters</td></tr><tr><td><code>[:blank:]</code></td><td>all horizontal whitespace</td></tr><tr><td><code>[:cntrl:]</code></td><td>all control characters</td></tr><tr><td><code>[:digit:]</code></td><td>all digits</td></tr><tr><td><code>[:graph:]</code></td><td>all printable characters, not including space</td></tr><tr><td><code>[:lower:]</code></td><td>all lower case letters</td></tr><tr><td><code>[:print:]</code></td><td>all printable characters, including space</td></tr><tr><td><code>[:punct:]</code></td><td>all punctuation characters</td></tr><tr><td><code>[:space:]</code></td><td>all horizontal or vertical whitespace</td></tr><tr><td><code>[:upper:]</code></td><td>all upper case letters</td></tr><tr><td><code>[:xdigit:]</code></td><td>all hexadecimal digits</td></tr><tr><td><code>[=CHAR=]</code></td><td>all characters which are equivalent to CHAR</td></tr></tbody></table>

***

## Examples

<table><thead><tr><th width="491">Commands</th><th>Description</th></tr></thead><tbody><tr><td><code>cat file.txt | tr -s '[a-z]' '[A-Z]'</code></td><td>Convert every alphabetic character to upper case</td></tr><tr><td><code>cat file.txt | tr -s '[:lower:]' '[:upper:]'</code></td><td>Convert every alphabetic character to upper case</td></tr><tr><td><code>cat creds.txt | tr -d '[a-zA-Z: ]'</code></td><td>To view creds of a user which are in digits</td></tr><tr><td><code>tr '()' '[]'</code></td><td>To  replace all parentheses ( ) with box brackets [ ]</td></tr><tr><td><code>tr -d a-z</code></td><td>To delete all the lowercase characters a-z</td></tr><tr><td><code>tr -s ' '</code></td><td>To replace all sequences of multiple spaces with just one space</td></tr><tr><td><code>tr [:space:] "\t"</code></td><td>Translates all the white-space characters to tabs</td></tr><tr><td><code>tr -d [:digit:]</code></td><td>To remove all the digits from the string</td></tr><tr><td><code>tr -cd [:digit:]</code></td><td>To remove all characters except digits ( complement )</td></tr><tr><td><code>tr -cs 'i' '0'</code></td><td>Replaces all characters except <code>i</code> with <code>0</code> and then squeezes the repeated <code>0</code> characters</td></tr><tr><td><code>tr -cs '[:alnum:]' '\n'</code></td><td>To put each word in a new line</td></tr><tr><td><code>tr -s '\n'</code></td><td>To delete the blank lines simply squeeze the repetitive newline characters</td></tr><tr><td><code>echo $PATH | tr ':' '\n'</code></td><td>To print each directory on a separate line from the PATH environment variable</td></tr></tbody></table>

