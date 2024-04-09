---
description: awk linux command cheatsheet by Thamizhiniyan C S
---

# awk

## Introduction

Awk is a scripting language used for manipulating data and generating reports.The awk command programming language requires no compiling, and allows the user to use variables, numeric functions, string functions, and logical operators.

***

## Syntax

```bash
awk [flags] [select pattern/find(sort)/commands] [input file]
```

***

## Program Structure

### BEGIN Block

{% tabs %}
{% tab title="Awk" %}
```awk
BEGIN {awk-commands}
```
{% endtab %}
{% endtabs %}

### BODY Block

{% tabs %}
{% tab title="Awk" %}
```awk
/pattern/ {awk-commands}
```
{% endtab %}
{% endtabs %}

### END Block

{% tabs %}
{% tab title="Awk" %}
```awk
END {awk-commands}
```
{% endtab %}
{% endtabs %}

***

## Important Flags

<table><thead><tr><th width="239">Flags</th><th>Description</th></tr></thead><tbody><tr><td><code>-F</code></td><td>With this flag you can specify FIELD SEPARATOR (FS), and thus don't need to use the BEGIN</td></tr><tr><td><code>-v</code></td><td>Can be used to specify variables(like we did in BEGIN{OFS=":"})</td></tr><tr><td><code>-D</code></td><td>You can debug your .awk scripts specifying this flag(awk -D script.awk)</td></tr><tr><td><code>-o</code></td><td>To specify the output file (if no name is given after the flag, the output is defaulted to awkprof.out)</td></tr><tr><td><code>f</code></td><td>Reads the AWK program source from the file program-file, instead of from the first command line argument</td></tr><tr><td><code>--dump-variables</code></td><td>Prints a sorted list of global variables and their final values to file</td></tr></tbody></table>

***

## Built in Variables

<table><thead><tr><th width="133">Variable</th><th width="185">Description</th><th>Example</th></tr></thead><tbody><tr><td><code>ARGC</code></td><td>It implies the number of arguments provided at the command line</td><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk 'BEGIN {print "Arguments =", ARGC}' One Two Three Four
</code></pre></td></tr><tr><td><code>ARGV</code></td><td>It is an array that stores the command-line arguments. The array's valid index ranges from 0 to ARGC-1</td><td><pre class="language-bash"><code class="lang-bash">awk 'BEGIN { 
   for (i = 0; i &#x3C; ARGC - 1; ++i) { 
      printf "ARGV[%d] = %s\n", i, ARGV[i] 
   } 
}' one two three four
</code></pre></td></tr><tr><td><code>CONVFMT</code></td><td>It represents the conversion format for numbers. Its default value is %.6g</td><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk 'BEGIN { print "Conversion Format =", CONVFMT }'
</code></pre></td></tr><tr><td><code>ENVIRON</code></td><td>It is an associative array of environment variables</td><td><pre class="language-bash"><code class="lang-bash">awk 'BEGIN { print ENVIRON["USER"] }
</code></pre></td></tr><tr><td><code>FILENAME</code></td><td>It represents the current file name</td><td><pre class="language-bash"><code class="lang-bash">awk 'END {print FILENAME}' marks.txt
</code></pre></td></tr><tr><td><code>FS</code></td><td>It represents the (input) field separator and its default value is space</td><td><pre class="language-bash"><code class="lang-bash">awk 'BEGIN {print "FS = " FS}' | cat -vte
</code></pre></td></tr><tr><td><code>NF</code></td><td>It represents the number of fields in the current record</td><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">echo -e "One Two\nOne Two Three\nOne Two Three Four" | awk 'NF > 2'
</code></pre></td></tr><tr><td><code>NR</code></td><td>It represents the number of the current record</td><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">echo -e "One Two\nOne Two Three\nOne Two Three Four" | awk 'NR &#x3C; 3'
</code></pre></td></tr><tr><td><code>FNR</code></td><td>It is similar to NR, but relative to the current file</td><td>-</td></tr><tr><td><code>OFMT</code></td><td>It represents the output format number and its default value is %.6g</td><td><pre class="language-bash"><code class="lang-bash">awk 'BEGIN {print "OFMT = " OFMT}'
</code></pre></td></tr><tr><td><code>OFS</code></td><td>It represents the output field separator and its default value is space</td><td><pre class="language-bash"><code class="lang-bash">awk 'BEGIN {print "OFS = " OFS}' | cat -vte
</code></pre></td></tr><tr><td><code>ORS</code></td><td>It represents the output record separator and its default value is newline</td><td><pre class="language-bash"><code class="lang-bash">awk 'BEGIN {print "ORS = " ORS}' | cat -vte
</code></pre></td></tr><tr><td><code>RLENGTH</code></td><td>It represents the length of the string matched by match function</td><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk 'BEGIN { if (match("One Two Three", "re")) { print RLENGTH } }'
</code></pre></td></tr><tr><td><code>RS</code></td><td>It represents (input) record separator and its default value is newline</td><td><pre class="language-bash"><code class="lang-bash">awk 'BEGIN {print "RS = " RS}' | cat -vte
</code></pre></td></tr><tr><td><code>RSTART</code></td><td>It represents the first position in the string matched by match function</td><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk 'BEGIN { if (match("One Two Three", "Thre")) { print RSTART } }'
</code></pre></td></tr><tr><td><code>SUBSEP</code></td><td>It represents the separator character for array subscripts and its default value is \034</td><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk 'BEGIN { print "SUBSEP = " SUBSEP }' | cat -vte
</code></pre></td></tr><tr><td><code>$0</code></td><td>It represents the entire input record</td><td><pre class="language-bash"><code class="lang-bash">awk '{print $0}' marks.txt
</code></pre></td></tr><tr><td><code>$n</code></td><td>It represents the nth field in the current record where the fields are separated by FS</td><td><pre class="language-bash"><code class="lang-bash">awk '{print $3 "\t" $4}' marks.txt
</code></pre></td></tr></tbody></table>

***

## printf statement

awk's printf statement is the same as that in C, except that the `*` format specifier is not supported.

**SYNTAX:** `printf`` `_`format`_`,`` `_`expr1`_`,`` `_`expr2`_`, ...,`` `_`exprn`_

### awk printf conversion characters

| Character | Prints expression as                                                          |
| --------- | ----------------------------------------------------------------------------- |
| `%c`      | single character                                                              |
| `%d`      | decimal integer                                                               |
| `%e`      | \[-]d.dprecisionE\[+-]dd                                                      |
| `%f`      | \[-]ddd.dprecision                                                            |
| `%g`      | e or f conversion, whichever is shorter, with nonsignificant zeros suppressed |
| `%o`      | unsigned octal number                                                         |
| `%s`      | string                                                                        |
| `%x`      | unsigned hexadecimal number                                                   |
| `%%`      | print a %; no argument is converted                                           |

### printf examples

| Command                                                                                      | Output       |
| -------------------------------------------------------------------------------------------- | ------------ |
| <pre class="language-awk"><code class="lang-awk">printf "%d", 99/2
</code></pre>             | 49           |
| <pre class="language-awk"><code class="lang-awk">printf "%e", 99/2
</code></pre>             | 4.950000e+01 |
| <pre class="language-awk"><code class="lang-awk">printf "%f", 99/2
</code></pre>             | 49.500000    |
| <pre class="language-awk"><code class="lang-awk">printf "%6.2f", 99/2
</code></pre>          | 49.50        |
| <pre class="language-awk"><code class="lang-awk">printf "%g", 99/2
</code></pre>             | 49.5         |
| <pre class="language-awk"><code class="lang-awk">printf "%o", 99/2
</code></pre>             | 61           |
| <pre class="language-awk"><code class="lang-awk">printf "%06o", 99/2
</code></pre>           | 000061       |
| <pre class="language-awk"><code class="lang-awk">printf "%x", 99/2
</code></pre>             | 31           |
| <pre class="language-awk"><code class="lang-awk">printf "|%s|", "January"
</code></pre>      | \|January\|  |
| <pre class="language-awk"><code class="lang-awk">printf "|%10s|", "January"
</code></pre>    | \| January\| |
| <pre class="language-awk"><code class="lang-awk">printf "|%-10s|", "January"
</code></pre>   | \|January \| |
| <pre class="language-awk"><code class="lang-awk">printf "|%.3s|", "January"
</code></pre>    | \|Jan\|      |
| <pre class="language-awk"><code class="lang-awk">printf "|%10.3s|", "January"
</code></pre>  | \| Jan\|     |
| <pre class="language-awk"><code class="lang-awk">printf "|%-10.3s|", "January"
</code></pre> | \|Jan \|     |
| <pre class="language-awk"><code class="lang-awk">printf "%%"
</code></pre>                   | %            |

***

## Examples

<table><thead><tr><th width="530">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash"><code class="lang-bash">awk '{print}' file.txt
</code></pre></td><td>To simply print a file</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">awk '/ctf/' file.txt 
</code></pre></td><td>To search for a pattern inside a file</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">awk '{print $1,$3}' file.txt 
</code></pre></td><td>To list the words that are at 1st and 3rd fields</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">awk '{print NR,$0}'
</code></pre></td><td>To number the lines</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk 'BEGIN {FS="o"} {print $2}' file.txt 
</code></pre></td><td>Split based on the character 'o'</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk "BEGIN {FS='o'} {print $1,$3} END{print 'Total Rows=',NR}"
</code></pre></td><td>Split with the character 'o' and print the total number of characters</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk 'BEGIN {RS="o"} {print $0}' file.txt 
</code></pre></td><td>Separate rows base with 'o'</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk 'BEGIN {OFS=":"} {print $1,$2,$3,$4}' file.txt
</code></pre></td><td>To specify field delimeter while outputing</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk 'BEGIN {ORS=":"} {print $0}' file.txt 
</code></pre></td><td>To specify record delimeter while outputing</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">awk '!($2 &#x26;&#x26; $3 &#x26;&#x26; $4) {print "Not all scores are available for " $1}'
</code></pre></td><td>Checks if fields 2, 3, and 4 are all empty. If they are, it prints a message indicating that not all scores are available for the item identified in the first field</td></tr><tr><td><pre class="language-gawk"><code class="lang-gawk">awk '{
    if ( $2 == "" || $3 == "" || $4 == "" ) {
        print "Not all scores are available for", $1;
    }
}'
</code></pre></td><td>Checks if fields 2, 3, and 4 are all empty. If they are, it prints a message indicating that not all scores are available for the item identified in the first field</td></tr><tr><td><pre class="language-awk"><code class="lang-awk">awk '{
    grade="Pass"
    if ( $2&#x3C;50 || $3&#x3C;50 || $4&#x3C;50) grade="Fail"
    print $1,":",grade
}'
</code></pre></td><td>Evaluates student scores and assigns a grade of "Pass" or "Fail" based on whether any of their scores are below 50. It then prints the student identifier along with their grade</td></tr><tr><td><pre class="language-awk"><code class="lang-awk">awk '{
    average = ( $2 + $3 + $4 ) / 3
    if ( average >= 80 ) print $0, ":", "A"
    else if ( average >= 60 ) print $0, ":", "B"
    else if ( average >= 50 ) print $0, ":", "C"
    else print $0, ":", "FAIL"
}'
</code></pre></td><td>To identify the performance grade for each student. If the average of the three scores is 80 or more, the grade is 'A'. If the average is 60 or above, but less than 80, the grade is 'B'. If the average is 50 or above, but less than 60, the grade is 'C'. Otherwise the grade is 'FAIL'.</td></tr><tr><td><pre class="language-awk"><code class="lang-awk">awk '{
    printf ($0)
    if ( NR % 2 == 0 ) printf "\n"
    else printf ";"
}'
</code></pre></td><td>Formats input data by printing each line as is, but inserts a newline character every two lines and a semicolon after every odd-numbered line. This formatting creates a specific structure in the output</td></tr></tbody></table>
