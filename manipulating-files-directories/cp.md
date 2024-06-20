---
description: cp linux command cheatsheet by Thamizhiniyan C S
---

# cp

## Introduction

The `cp` command is used to copy files and directories.

***

## Syntax

`cp [OPTION]... [-T] SOURCE DEST`

`cp [OPTION]... SOURCE... DIRECTORY`

`cp [OPTION]... -t DIRECTORY SOURCE...`

***

## Important Flags

<table><thead><tr><th width="373">Flag</th><th>Description</th></tr></thead><tbody><tr><td><code>-a, --archive</code></td><td>Preserve the source's metadata, such as creation date, permissions, and extended attributes.</td></tr><tr><td><code>-b, --backup</code></td><td>Create backups for destination files. The backup file has the (~) suffix unless --suffix is used.</td></tr><tr><td><code>-f, --force</code></td><td>If the destination file/directory already exists, replace it with the source.</td></tr><tr><td><code>-i, --interactive</code></td><td>Ask before overwriting the destination with the source.</td></tr><tr><td><code>-l, --link</code></td><td>Create hard links instead of new files. The destination file will have the same inode attribute as the source.</td></tr><tr><td><code>-n, --no-clobber</code></td><td>Do not overwrite the destination file if it exists.</td></tr><tr><td><code>-R, -r, --recursive</code></td><td>Copy the source directory recursively.</td></tr><tr><td><code>-S, --suffix=</code></td><td>Provide a custom suffix for the backup file.</td></tr><tr><td><code>-t, --target-directory=</code></td><td>Specify a directory for the source files.</td></tr><tr><td><code>-u, --update</code></td><td>Replace files only if they satisfy the update condition. The short option replaces files if the destination is older than the source. The long option lets the user specify the condition (all, none, or older).</td></tr><tr><td><code>-v, --verbose</code></td><td>Output information about the copying process.</td></tr><tr><td><code>-p</code></td><td>Preserves file characteristics (modification time, access time, ownership, permission-bits).</td></tr><tr><td><code>*</code></td><td>Uses the * wildcard to represent all files and directories matching a pattern.</td></tr><tr><td><code>--help</code></td><td>Show help.</td></tr><tr><td><code>--version</code></td><td>Show version information.</td></tr></tbody></table>

***

## Examples

<table><thead><tr><th width="375">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp file-1.txt file-2.txt file-3.txt test-dir
</code></pre></td><td>Copy file-1.txt, file-2.txt, and file-3.txt to the test-dir directory.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp file-* test-dir
</code></pre></td><td>Copy all files starting with file- to test-dir using the * wildcard.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -v -i file-1.txt test-dir
</code></pre></td><td>Copy file-1.txt to test-dir with verbose output. Prompt to overwrite if the file exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -v -b -S .bak file-1.txt test-dir
</code></pre></td><td>Copy file-1.txt to test-dir, creating a backup file with .bak extension. Show verbose output.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp Src_file Dest_file
</code></pre></td><td>Copy contents of Src_file to Dest_file. Overwrites Dest_file if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp a.txt b.txt
</code></pre></td><td>Copy contents of a.txt to b.txt. Overwrites b.txt if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp a.txt c.txt
</code></pre></td><td>Copy contents of a.txt to c.txt. Overwrites c.txt if it exists.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp Src_file1 Src_file2 Src_file3 Dest_directory
</code></pre></td><td>Copy Src_file1, Src_file2, and Src_file3 to Dest_directory. Overwrites existing files in Dest_directory.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp a.txt b.txt c.txt new/
</code></pre></td><td>Copy a.txt, b.txt, and c.txt to new/ directory. Overwrites existing files in new/.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -R Src_directory Dest_directory
</code></pre></td><td>Recursively copy all files from Src_directory to Dest_directory.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -i [Source_file] [Destination_file]
</code></pre></td><td>Interactive copying: prompts before overwriting Destination_file. Press 'y' to confirm overwrite.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -i a.txt b.txt
</code></pre></td><td>Interactive copy of a.txt to b.txt. Prompts to confirm overwrite of b.txt.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -f [Source_file] [Destination_file]
</code></pre></td><td>Force copying: deletes Destination_file if unable to write, then copies Source_file.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -f a.txt b.txt
</code></pre></td><td>Forceful copy of a.txt to b.txt. Overwrites b.txt without prompting.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -r [Directory_name1] [Directory_name2]
</code></pre></td><td>Recursive copy of Directory_name1 contents to Directory_name2.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -r source_directory dest_directory
</code></pre></td><td>Recursively copy contents of source_directory to dest_directory.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -p [Source_file] [Destination_file]
</code></pre></td><td>Preserve copying: retains original file characteristics (timestamps, ownership, permissions) in Destination_file.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp -p a.txt c.txt
</code></pre></td><td>Preserves characteristics of a.txt when copying to c.txt.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp *.txt [Destination Directory or file]
</code></pre></td><td>Copy all .txt files to Destination Directory or file using * wildcard.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cp *.txt Folder1
</code></pre></td><td>Copy all .txt files to Folder1 using * wildcard.</td></tr></tbody></table>
