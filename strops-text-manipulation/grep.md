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

| Command                                                                                                                  | Description                                                               |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep "literal_string" filename
</code></pre>     | Search for the given string in a single file                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep "string" FILE_PATTERN
</code></pre>         | Checking for the given string in multiple files                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -i "string" FILE
</code></pre>              | Case insensitive search                                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep "REGEX" filename
</code></pre>              | Match regular expression in files                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -iw "is" demo_file
</code></pre>            | Checking for full words, not for sub-strings using grep -w                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -A  "string" FILENAME
</code></pre>         | Display N lines after match                                               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -B  "string" FILENAME
</code></pre>         | Display N lines before match                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -C  "string" FILENAME
</code></pre>         | Display N lines around match                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -r "ramesh" *
</code></pre>                 | Searching in all files recursively using grep -r                          |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -v "go" demo_text
</code></pre>             | Invert match using grep -v                                                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -v -e "pattern" -e "pattern"
</code></pre>  | Display the lines which does not matches all the given pattern            |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -c "pattern" filename
</code></pre>         | Counting the number of matches using grep -c                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -l this demo_*
</code></pre>                | Display only the file names which matches the given pattern using grep -l |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -o "is.*line" demo_file
</code></pre>       | Show only the matched string                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -o -b "pattern" file
</code></pre>          | Show the position of match in the line                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -n "go" demo_text
</code></pre>             | Show line number while displaying the output using grep -n                |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">grep -iRl [directory path/keyword]
</code></pre> | Find files with a specific keyword                                        |
