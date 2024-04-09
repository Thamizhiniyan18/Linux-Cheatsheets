---
description: grep linux command cheatsheet by Thamizhiniyan C S
---

# grep

## Introduction

The grep filter searches a file for a particular pattern of characters, and displays all lines that contain that pattern. The pattern that is searched in the file is referred to as the regular expression.

***

## Important Flags

<table><thead><tr><th width="105">Flags</th><th>Description</th></tr></thead><tbody><tr><td><code>-R</code></td><td>Does a recursive grep search for the files inside the folders(if found in the specified path for pattern search; else grep won't traverse directory for searching the pattern you specify)</td></tr><tr><td><code>-h</code></td><td>If you're grepping recursively in a directory, this flag disables the prefixing of filenames in the results.</td></tr><tr><td><code>-c</code></td><td>This flag won't list you the pattern only list an integer value, that how many times the pattern was found in the file/folder.</td></tr><tr><td><code>-i</code></td><td>Specifies grep to search for the PATTERN while IGNORING the case</td></tr><tr><td><code>-l</code></td><td>Will only list the filename instead of pattern found in it.</td></tr><tr><td><code>-n</code></td><td>It will list the lines with their line number in the file containing the pattern.</td></tr><tr><td><code>-v</code></td><td>This flag prints all the lines that are NOT containing the pattern</td></tr><tr><td><code>-E</code></td><td>This flag we already read above... will consider the PATTERN as a regular expression to find the matching strings.</td></tr><tr><td><code>-e</code></td><td>The official documentation says, it can be used to specify multiple patterns and if any string matches with the pattern(s) it will list it.</td></tr></tbody></table>

***

## Examples

<table><thead><tr><th width="389">Command</th><th>Description</th></tr></thead><tbody><tr><td><code>grep "literal_string" filename</code></td><td>Search for the given string in a single file</td></tr><tr><td><code>grep "string" FILE_PATTERN</code></td><td>Checking for the given string in multiple files</td></tr><tr><td><code>grep -i "string" FILE</code></td><td>Case insensitive search</td></tr><tr><td><code>grep "REGEX" filename</code></td><td>Match regular expression in files</td></tr><tr><td><code>grep -iw "is" demo_file</code></td><td>Checking for full words, not for sub-strings using grep -w</td></tr><tr><td><code>grep -A &#x3C;N> "string" FILENAME</code></td><td>Display N lines after match</td></tr><tr><td><code>grep -B &#x3C;N> "string" FILENAME</code></td><td>Display N lines before match</td></tr><tr><td><code>grep -C &#x3C;N> "string" FILENAME</code></td><td>Display N lines around match</td></tr><tr><td><code>grep -r "ramesh" *</code></td><td>Searching in all files recursively using grep -r</td></tr><tr><td><code>grep -v "go" demo_text</code></td><td>Invert match using grep -v</td></tr><tr><td><code>grep -v -e "pattern" -e "pattern"</code></td><td>Display the lines which does not matches all the given pattern</td></tr><tr><td><code>grep -c "pattern" filename</code></td><td>Counting the number of matches using grep -c</td></tr><tr><td><code>grep -l this demo_*</code></td><td>Display only the file names which matches the given pattern using grep -l</td></tr><tr><td><code>grep -o "is.*line" demo_file</code></td><td>Show only the matched string</td></tr><tr><td><code>grep -o -b "pattern" file</code></td><td>Show the position of match in the line</td></tr><tr><td><code>grep -n "go" demo_text</code></td><td>Show line number while displaying the output using grep -n</td></tr><tr><td><code>grep -iRl [directory path/keyword]</code></td><td>Find files with a specific keyword</td></tr></tbody></table>
