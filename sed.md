---
description: sed linux command cheatsheet by Thamizhiniyan C S
---

# sed

## Introduction

Sed is a Stream Editor used for modifying the files in unix (or linux).

***

## Syntax

```bash
sed [flags] [pattern/script] [input file]
```

{% code overflow="wrap" %}
```
'[condition(s)(optional)] [command/mode(optional)]/[source/to-be-searched pattern(mandatory)]/[to-be-replaced pattern(depends on command/mode you use)]/[args/flags to operate on the pattern searched(optional)]'
```
{% endcode %}

***

## Important Flags

<table><thead><tr><th width="106">Flags</th><th>Description</th></tr></thead><tbody><tr><td>-e</td><td>To add a script/command that needs to be executed with the pattern/script(on searching for pattern)</td></tr><tr><td>-f</td><td>Specify the file containing string pattern</td></tr><tr><td>-E</td><td>Use extended regular expressions </td></tr><tr><td>-n</td><td>Suppress the automatic printing or pattern spacing</td></tr></tbody></table>

***

## Modes / Commands

<table><thead><tr><th width="142">Commands</th><th>Description</th></tr></thead><tbody><tr><td>s</td><td>(Most used)Substitute mode (find and replace mode)</td></tr><tr><td>y</td><td>Works same as substitution; the only difference is, it works on individual bytes in the string provided(this mode takes no arguments/conditions)</td></tr></tbody></table>

***

## Arguments

<table><thead><tr><th width="140">Flags/Args</th><th>Description</th></tr></thead><tbody><tr><td>/g</td><td>globally(any pattern change will be affected globally, i.e. throughout the text; generally works with s mode) </td></tr><tr><td>/i</td><td>To make the pattern search case-insensitive(can be combined with other flags)</td></tr><tr><td>/d</td><td>To delete the pattern found(Deletes the whole line; takes no parameter like conditions/modes/to-be-replaced string)</td></tr><tr><td>/p</td><td>prints the matching pattern(a duplicate will occur in output if not suppressed with -n flag.)</td></tr><tr><td>/1,/2,/3../n</td><td>To perform an operation on an nth occurrence in a line(works with s mode)</td></tr></tbody></table>

***

## Examples

<table data-full-width="false"><thead><tr><th width="395">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/unix/linux/' file.txt
</code></pre></td><td>Replacing or substituting string</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/unix/linux/2' file.txt
</code></pre></td><td>Replacing the nth occurrence of a pattern in a line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/unix/linux/g' file.txt
</code></pre></td><td>Replacing all the occurrence of the pattern in a line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/unix/linux/3g' file.txt
</code></pre></td><td>Replacing from nth occurrence to all occurrences in a line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's_http://_www_' file.txt
</code></pre></td><td>Changing the slash (/ -> _) delimiter</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/unix/{&#x26;}/' file.txt
</code></pre></td><td>Using &#x26; as the matched string ( adding curly braises )</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/(unix)/11/' file.txt
</code></pre></td><td>Replace the word “unix” in a line with twice as the word like “unixunix”</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/(unix)(linux)/21/' file.txt
</code></pre></td><td>Switch the words “unixlinux” as “linuxunix”</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/^(.)(.)(.)/321/' file.txt
</code></pre></td><td>Switching the first three characters in a line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/unix/linux/p' file.txt
</code></pre></td><td>Duplicating the replaced line with /p flag</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed -n 's/unix/linux/p' file.txt
</code></pre></td><td>Printing only the replaced lines</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed 's/unix/linux/' file.txt | sed 's/os/system/'
</code></pre></td><td>Run multiple sed commands by piping the output of one sed command as input to another sed command</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed -e 's/unix/linux/' -e 's/os/system/' file.txt
</code></pre></td><td>To run multiple sed commands in a single sed command</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed '3 s/unix/linux/' file.txt
</code></pre></td><td>Replacing string on a specific line number</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed '1,3 s/unix/linux/' file.txt
</code></pre></td><td>Replacing string on a range of lines</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed '2,$ s/unix/linux/' file.txt
</code></pre></td><td>Replacing the text from second line to last line in the file</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed '/linux/ s/unix/centos/' file.txt
</code></pre></td><td>Replace on a lines which matches a pattern. Here the sed command first looks for the lines which has the pattern “linux” and then replaces the word “unix” with “centos”</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed '2 d' file.txt
</code></pre></td><td>Deleting lines</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 'p' file.txt
</code></pre></td><td>Duplicating lines</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed -n '/unix/ p' file.txt
</code></pre></td><td>Sed as grep command</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed '/unix/ a "Add a new line"' file.txt
</code></pre></td><td>Add a line after a match</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed '/unix/ i "Add a new line"' file.txt
</code></pre></td><td>Add a line before a match</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed '/unix/ c "Change line"' file.txt
</code></pre></td><td>Change a line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 'y/ul/UL/' file.txt
</code></pre></td><td>Transform like tr command</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/\bthe\b/this/'
</code></pre></td><td>Transform the first occurrence of the word 'the' with 'this' in each line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/\bthy\b/your/Ig'
</code></pre></td><td>Case Insensitive transform all the occurrences of the word 'thy' with 'your'</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/thy/{&#x26;}/Ig'
</code></pre></td><td>Case Insensitive. Highlight all the occurrences of 'thy' by wrapping them up in brace brackets</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed 's/\(\d\{4\}\s\)\{2\}\(\d\{4\}\)/**** **** ****/g'
</code></pre></td><td>Replace occurrences of credit card numbers in the format XXXX XXXX XXXX with a masked version **** **** **** in each line</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed -E 's/([0-9]+) ([0-9]+) ([0-9]+) ([0-9]+)/\4 \3 \2 \1/' 
</code></pre></td><td>Rearranges these groups in reverse order, separated by whitespace, effectively reversing the order of the groups of digits in each line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/hack/back/3' file.txt
</code></pre></td><td>Substitute every 3rd occurrence of the word 'hack' to 'back' on every line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed '3,4 s/hack/back/3' file.txt
</code></pre></td><td>Substitute every 3rd occurrence of the word 'hack' to 'back' on 3rd and 4th line</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">sed 's/  */:/g' sed1.txt
</code></pre></td><td>Formatting the trailing spaces in sed1.txt with a colon(:)</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed 's/\(^\b[[:alpha:] ]*\)\([[:digit:]]*\)/\=\> \1\[\2\]/g' file.txt
</code></pre></td><td>Making every line to start with a bullet point and enclose the digits in square brackets using regex</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">sed -e 's/[[:digit:]]//g' -e 's/  *//'g sed2.txt
</code></pre></td><td>Remove all digits and replace trailing spaces into a single space</td></tr></tbody></table>
