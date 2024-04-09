---
description: du linux command cheatsheet by Thamizhiniyan C S
---

# du

## Introduction

`du` is a command in linux (short for disk usage) which helps you identify what files/directories are consuming how much space.

***

## Important Flags

<table><thead><tr><th width="167">Flag</th><th>Description</th></tr></thead><tbody><tr><td>-a</td><td>Will list files as well with the folder.</td></tr><tr><td>-h</td><td>Will list the file sizes in human readable format(B,MB,KB,GB)</td></tr><tr><td>-c</td><td>Using this flag will print the total size at the end. Jic you want to find the size of directory you were enumerating</td></tr><tr><td>-d &#x3C;number></td><td>Flag to specify the depth-ness of a directory you want to view the results for (eg. -d 2)</td></tr><tr><td>--time </td><td>To get the results with time stamp of last modified.</td></tr></tbody></table>

***

## Examples

`du -a /home/`

`du --time -d 1 /home/`
