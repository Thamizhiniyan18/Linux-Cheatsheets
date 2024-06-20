---
description: mv linux command cheatsheet by Thamizhiniyan C S
---

# mv

## Introduction

This command is used to move the files and directories from the source to destination. Also used for renaming files.

***

## Syntax

`mv [OPTION]... [-T] SOURCE DEST`&#x20;

`mv [OPTION]... SOURCE... DIRECTORY`&#x20;

`mv [OPTION]... -t DIRECTORY SOURCE...`

***

## Important Flags

| Flag                | Description                                                                                    |
| ------------------- | ---------------------------------------------------------------------------------------------- |
| `-b, --backup`      | Create a backup of files that will be overwritten or removed.                                  |
| `-f, --force`       | Overwrite destination files without prompting the user.                                        |
| `-i, --interactive` | Prompt the user to confirm if the mv action should overwrite a file.                           |
| `-S, --suffix=`     | Provide a suffix for a backup file. The default suffix is \~.                                  |
| `-u, --update`      | Perform the mv action only if the source file is newer or the destination file does not exist. |
| `-v, --verbose`     | Show an output describing the action taken.                                                    |
| `--help`            | Output the command help and exit.                                                              |
| `--version`         | Show the command version and exit.                                                             |

***

## Examples

<table><thead><tr><th width="375">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv name1 name2
</code></pre></td><td>Rename the file name1 to name2. The command produces no output, but ls confirms the operation was successful.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv filename /path/to/destination/
</code></pre></td><td>To move a file from one folder to another</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv directory_name /path/to/destination/
</code></pre></td><td>To move an entire directory</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv [source_file_name(s)] [Destination_file_name]
</code></pre></td><td>Rename a file: Rename source_file_name to Destination_file_name. Overwrites Destination_file_name if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv filename2 filename1
</code></pre></td><td>Renames filename2 to filename1. Overwrites filename1 if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv [source_file_name(s)] [Destination_path]
</code></pre></td><td>Move a file: Move source_file_name(s) to Destination_path.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv filename1 /home/user/test/
</code></pre></td><td>Moves filename1 to /home/user/test/.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv [source_file_name_1] [source_file_name_2] [...] [Destination_path]
</code></pre></td><td>Move multiple files: Move source_file_name_1, source_file_name_2, etc., to Destination_path.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv file_1 file_2 /home/user/test/
</code></pre></td><td>Moves file_1 and file_2 to /home/user/test/.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv [source_directory_name(s)] [Destination_directory_name]
</code></pre></td><td>Rename directory: Rename source_directory_name(s) to Destination_directory_name. Overwrites Destination_directory_name if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv test new_file
</code></pre></td><td>Renames test to new_file. Overwrites new_file if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv -i filename2 filename1
</code></pre></td><td>Renames filename2 to filename1, prompts for confirmation if filename1 exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv -v name1 name2 name3 test-dir
</code></pre></td><td>Move the files name1, name2, and name3 to test-dir in the home directory and show verbose output. The output confirms successful file movement.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv -v name1 name2
</code></pre></td><td>Rename the file name1 to name2 and print the output. This command produces an output listing the performed actions.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv -v -i name1 name2
</code></pre></td><td>Rename name1 to name2, prompting for confirmation if name2 already exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv -f file filename1
</code></pre></td><td>Forcefully renames file to filename1, overwriting filename1 if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv -n oldfile newfile
</code></pre></td><td>Renames oldfile to newfile, does not overwrite newfile if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv -b first_file second_file
</code></pre></td><td>Renames first_file to second_file, creates a backup of second_file if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">mv --version
</code></pre></td><td>Displays the version of mv.</td></tr></tbody></table>
