# Combos

## Introduction

This section consists of various combinations of commands from the "STROPS / Text Manipulation" section.

***

## Execute Commands from File

Executes each command from the first field of `commands.txt` using `awk` to parse and `xargs` to run them.

### Example File

```
id : Print the current user's UID and GID.
id -u root : Find the UID of the user named "root".
id -g root : Find the GID of the user named "root".
id root : Find the UID and all groups associated with the user "root".
id -G root : Display the UID and all groups a user "root" belongs to.
id -ng root : Display the name instead of numbers for GID of "root".
id -nu root : Display the name instead of numbers for UID of "root".
id -nG root : Display the name instead of numbers for all groups of "root".
id -r -g root : Display the real GID instead of effective GID of "root".
id -r -u root : Display the real UID instead of effective UID of "root".
id -r -G root : Display the real group IDs instead of effective groups of "root".
```

### Command

{% code overflow="wrap" %}
```bash
awk 'BEGIN {FS=":"} {print $1}' commands.txt | xargs -I command bash -c 'eval command'
```
{% endcode %}

### Output

```
uid=1000(user) gid=1001(user) groups=1001(group),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),106(netdev),114(bluetooth),117(lpadmin),120(scanner),993(bumblebee),1000(docker)
0
0
uid=0(root) gid=0(root) groups=0(root)
0
root
root
root
0
0
0
```

***
