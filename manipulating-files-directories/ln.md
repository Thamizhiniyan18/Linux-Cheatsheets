---
description: ln linux command cheatsheet by Thamizhiniyan C S
---

# ln

## Introduction

The `ln` command is used to create hard links and soft links for files in Linux.

***

## Syntax

`ln [OPTION]... [-T] TARGET LINK_NAME`

`ln [OPTION]... TARGET`

`ln [OPTION]... TARGET... DIRECTORY`

`ln [OPTION]... -t DIRECTORY TARGET...`

***

## Important Flags

<table><thead><tr><th width="378">Flag</th><th>Description</th></tr></thead><tbody><tr><td><code>--backup[=CONTROL]</code></td><td>make a backup of each existing destination file</td></tr><tr><td><code>-b</code></td><td>like --backup but does not accept an argument</td></tr><tr><td><code>-d, -F, --directory</code></td><td>allow the superuser to attempt to hard link directories (note: will probably fail due to system restrictions, even for the superuser)</td></tr><tr><td><code>-f, --force</code></td><td>remove existing destination files</td></tr><tr><td><code>-i, --interactive</code></td><td>prompt whether to remove destinations</td></tr><tr><td><code>-L, --logical</code></td><td>dereference TARGETs that are symbolic links</td></tr><tr><td><code>-n, --no-dereference</code></td><td>treat LINK_NAME as a normal file if it is a symbolic link to a directory</td></tr><tr><td><code>-P, --physical</code></td><td>make hard links directly to symbolic links</td></tr><tr><td><code>-r, --relative</code></td><td>with -s, create links relative to link location</td></tr><tr><td><code>-s, --symbolic</code></td><td>make symbolic links instead of hard links</td></tr><tr><td><code>-S, --suffix=SUFFIX</code></td><td>override the usual backup suffix</td></tr><tr><td><code>-t, --target-directory=DIRECTORY</code></td><td>specify the DIRECTORY in which to create the links</td></tr><tr><td><code>-T, --no-target-directory</code></td><td>treat LINK_NAME as a normal file always</td></tr><tr><td><code>-v, --verbose</code></td><td>print name of each linked file</td></tr><tr><td><code>--help</code></td><td>display this help and exit</td></tr><tr><td><code>--version</code></td><td>output version information and exit</td></tr></tbody></table>

***

## Hard Link

* Hard links are the original Unix method of creating links.
* Every file has at least one hard link by default, which gives it a name.
* Creating a hard link adds another directory entry for the same file.
* Hard links are indistinguishable from the original file itself in directory listings.
* When a hard link is deleted, the link itself is removed, but the file's contents remain until all links to it are deleted.
* Limitations of hard links:
  * Cannot reference a file outside its own file system (same disk partition).
  * Cannot reference a directory.

***

## Soft Link (aka Symbolic Link )

* Symbolic links (symlinks) were introduced to overcome the limitations of hard links.
* They create a special type of file that contains a text pointer to the referenced file or directory.
* Similar to Windows shortcuts, symlinks allow referencing files or directories.
* A symbolic link and the file it points to are almost indistinguishable; operations on the symlink affect the referenced file.
* Deleting a symbolic link removes only the link itself, not the referenced file.
* If the referenced file is deleted, the symlink becomes broken, pointing to nothing.
* Many implementations of the `ls` command display broken symlinks in a distinguishing color (e.g., red) to indicate their presence.

***

## Soft Links vs. Hard Links

Source: [https://phoenixnap.com/kb/symbolic-link-linux](https://phoenixnap.com/kb/symbolic-link-linux)

<table><thead><tr><th width="208">Category</th><th>Soft Link (aka Symbolic Link )</th><th>Hard Link</th></tr></thead><tbody><tr><td>Reference Type</td><td>Follows a path to a file or a directory.</td><td>Points to the actual file data on the storage volume.</td></tr><tr><td>Compatible Targets</td><td>Uses files and directories on local and external volumes.</td><td>Can be created only locally as it references a physical location on the volume</td></tr><tr><td>Target Dependence</td><td>Does not work after its target file is moved or deleted.</td><td>Works after the target file is moved or deleted.</td></tr><tr><td>Usage</td><td>Offers quick access to a frequently-used file.</td><td>Provides flexibility when organizing a filesystem.</td></tr></tbody></table>

***

## Examples

<table><thead><tr><th width="381">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">ln [target/file] [symlink]
</code></pre></td><td>To create a hard link to a file</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">ln -s [target/file] [symlink]
</code></pre></td><td>To create a symbolic link to a file</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">ln -s test/target-file.txt link-file.txt
</code></pre></td><td>Creates a symbolic link (link-file.txt) that points to the target file (target-file.txt) located in the test directory.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">ln -s [target-directory] [symlink]
</code></pre></td><td>To create a symbolic link to a directory</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">ln -sf [target] [destination]
</code></pre></td><td>Overwriting Symbolic Links. Using the -f option permanently deletes the existing file.</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">unlink [symlink/link_file]
</code></pre></td><td>Removing the symbolic link</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">rm [symlink/link_file]
</code></pre></td><td>Removing the symbolic link</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">find [directory] -type l ! -exec test -e {} \; -print | while read line; do unlink "$line"; done
</code></pre></td><td>To perform the search and locate the links that do not work (Find all Broken Symbolic Links) and remove them</td></tr></tbody></table>
