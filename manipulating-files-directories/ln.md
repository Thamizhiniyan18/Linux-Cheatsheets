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

