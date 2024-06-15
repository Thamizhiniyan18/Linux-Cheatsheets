---
description: cut linux command cheatsheet by Thamizhiniyan C S
---

# cut

## Introduction

The cut command is used to remove sections from each line of files.

***

## Syntax

`cut OPTION... [FILE]...`

***

## Important Flags

<table><thead><tr><th width="274">Flag</th><th>Description</th></tr></thead><tbody><tr><td><code>-b, --bytes=LIST</code></td><td>Selects only the bytes specified in LIST (e.g., -b 1-3,7).</td></tr><tr><td><code>-c, --characters=LIST</code></td><td>Selects only the characters specified in LIST (e.g., -c 1-3,7).</td></tr><tr><td><code>-d, --delimiter=DELIM</code></td><td>Uses DELIM as the field delimiter character instead of the tab character. (default: TAB)</td></tr><tr><td><code>-f, --fields=LIS</code></td><td>Selects only the fields specified in LIST, separated by the delimiter character (default is tab).</td></tr><tr><td><code>-n</code></td><td>Do not split multi-byte characters (no effect unless -b or -c is specified).</td></tr><tr><td><code>-s</code></td><td>do not print lines not containing delimiter</td></tr><tr><td><code>-z</code></td><td>line delimiter is NUL, not newline</td></tr><tr><td><code>–complement</code></td><td>Invert the selection of fields/characters. Print the fields/characters not selected.</td></tr></tbody></table>

***

## Examples

<table data-full-width="false"><thead><tr><th width="335">Command</th><th width="364">Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -b 1,2,3 readme.txt
</code></pre></td><td>Extract specific bytes: 1, 2, and 3 from each line of the file.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -b 1-3,5-7 readme.txt
</code></pre></td><td>Extract specific bytes with ranges: 1-3 and 5-7 from each line of the file.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -b 1- readme.txt
</code></pre></td><td>Extract bytes from the beginning to the end of each line.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -b -3 readme.txt
</code></pre></td><td>Extract bytes from the beginning up to the 3rd byte of each line.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c 1-7 readme.txt
</code></pre></td><td>Extract the first seven characters from each line of the file.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c 2,5,7 readme.txt
</code></pre></td><td>Extract specific characters: 2, 5, and 7 from each line of the file.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c 1- readme.txt
</code></pre></td><td>Extract characters from the beginning to the end of each line.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c -5 readme.txt
</code></pre></td><td>Extract characters from the beginning up to the 5th character of each line.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c 5-10 text.txt
</code></pre></td><td>Extract characters 5 to 10 from each line of the file named text.txt.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c 1-5,10-15 data.txt
</code></pre></td><td>Extract characters 1 to 5 and 10 to 15 from each line of the file data.txt.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c 3
</code></pre></td><td>To print the 3rd character from each line as a new line of output</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c 2,7
</code></pre></td><td>Display the 2nd and 7th character from each line of text.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c 2-7
</code></pre></td><td>Display a range of characters starting at the 2nd position of a string and ending at the 7th position (both positions included)</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c -4
</code></pre></td><td>Display the first four characters from each line of text.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -c 13-
</code></pre></td><td>Print the characters from thirteenth position to the end.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut --complement -d " " -f 1 readme.txt
</code></pre></td><td>Extract all fields except the first field using space as the field separator.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut --complement -c 5 readme.txt
</code></pre></td><td>Extract all characters except the 5th character from each line of the file.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -d " " -f 1 readme.txt
</code></pre></td><td>Extract the first field from each line using space as the field separator.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -d " " -f 1-4 readme.txt
</code></pre></td><td>Extract fields 1 to 4 from each line using space as the field separator.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -d " " -f 1,2 readme.txt --output-delimiter='%'
</code></pre></td><td>Extract fields 1 and 2 from each line using space as the field separator, with '%' as output delimiter.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat readme.txt \| cut -d ' ' -f 1 \| sort -r
</code></pre></td><td>Extract the first field from each line and sort the output in reverse order.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat readme.txt \| head -n 3 \| cut -d ' ' -f 1 > list.txt
</code></pre></td><td>Extract the first field from the first 3 lines and redirect the output to list.txt.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -d',' -f1,3 data.csv
</code></pre></td><td>Extract the first and third columns from a CSV file named data.csv.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -d':' -f1,3 data.txt
</code></pre></td><td>Extract the first and third fields from the file data.txt using colon as the delimiter.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -d',' -f1,3 data.csv > output.txt
</code></pre></td><td>Extract the first and third fields from the file data.csv and store the output in output.txt.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -d ' ' -f 4
</code></pre></td><td>Given a sentence, identify and display its fourth word. Assume that the space (' ') is the only delimiter between words.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -d ' ' -f -3
</code></pre></td><td>Given a sentence, identify and display its first three words. Assume that the space (' ') is the only delimiter between words.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -f 1 readme.txt
</code></pre></td><td>Extract the first field from each line of the file using the default tab delimiter.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -f -3
</code></pre></td><td>Given a tab delimited file with several columns (tsv format) print the first three fields.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut -f 2-
</code></pre></td><td>Given a tab delimited file with several columns (tsv format) print the fields from second fields to last field.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cut --version
</code></pre></td><td>Display the version of the cut command.</td></tr></tbody></table>

