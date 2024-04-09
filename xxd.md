---
description: xxd linux command cheatsheet by Thamizhiniyan C S
---

# xxd

## Introduction

xxd creates a hex dump of a given file or standard input. It can also convert a hex dump back to its original binary form.

***

## Syntax

`xxd -h[elp]`&#x20;

`xxd [options] [infile [outfile]]`&#x20;

`xxd -r[evert] [options] [infile [outfile]]`

***

## Important Flags

<table><thead><tr><th width="118">Flags</th><th>Description</th></tr></thead><tbody><tr><td><code>-b</code></td><td>will give binary representation instead of hexdump</td></tr><tr><td><code>-E</code></td><td>Change the character encoding in the right hand column from ASCII to EBCDIC (Feel free to leave this flag if you don't know about BCD notation)</td></tr><tr><td><code>-c</code></td><td>int Sets the number of bytes to be represented in one row. (i.e. setting the column size in bytes; Default to 16)</td></tr><tr><td><code>-g</code></td><td>This flag is to set how many bytes/octets should be in a group i.e. separated by a whitespace (default to 2 bytes; Set -g0 if no space is needed).</td></tr><tr><td><code>-i</code></td><td>To output the hexdump in C include format ('0xff' integers)</td></tr><tr><td><code>-l</code></td><td>Specify the length of output(if the string is bigger than the length specified, hex of the rest of the string will not be printed)</td></tr><tr><td><code>-p</code></td><td>Second most used flag; Converts the string passed into plain hexdump style(continuous string of hex bytes)</td></tr><tr><td><code>-r</code></td><td>Most used flag, will revert the hexdump to binary(Interpreted as plain text).</td></tr><tr><td><code>-u</code></td><td>Use uppercase hex letters(default is lower case)</td></tr><tr><td><code>-s</code></td><td>seek at offset (will discuss this in a little brief in examples)</td></tr></tbody></table>

***

## Examples

<table><thead><tr><th width="427">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">echo "hello world foo bar fiz" | xxd
</code></pre></td><td>It will produce a hexdump of the string "hello world foo bar fiz"</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">echo "hello world foo bar fiz" | xxd -E
</code></pre></td><td>Change the character encoding in the right hand column from ASCII to EBCDIC</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">echo "hello world foo bar fiz" | xxd -b
</code></pre></td><td>Will give binary representation instead of hexdump</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">echo "hello world foo bar fiz" | xxd -i
</code></pre></td><td>To output the hexdump in C include format</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">echo "hello world foo bar fiz" | xxd -l 12
</code></pre></td><td>It will display the hexdump of the first 12 bytes of the input string "hello world foo bar fiz"</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">xxd -s 0x10 xxd.txt
</code></pre></td><td>Seeking an offset </td></tr><tr><td><pre class="language-bash"><code class="lang-bash">xxd -s -16 xxd.txt
</code></pre></td><td>Seeking at offset from the end of the file</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">xxd -c 3 -g 3 file.txt
</code></pre></td><td>To display a n bytes of hexdump in 3 columns with a group of 3 octets per row from file.txt</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">xxd -s 0xa -l 50 -b file.txt
</code></pre></td><td>Seek at 10th byte(in hex) in file.txt and display only 50 bytes</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">xxd -r -p file.txt
</code></pre></td><td>To read plain hexadecimal dumps</td></tr></tbody></table>
