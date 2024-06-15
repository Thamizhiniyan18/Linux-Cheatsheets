---
description: pwd linux command cheatsheet by Thamizhiniyan C S
---

# pwd

## Introduction

The **`pwd`** Linux command prints the current working directory path, starting from the root (**`/`**). This command is used to Print the name of the current working directory.

***

## Syntax

`pwd [OPTION]...`

***

## Important Flags

| Flag                   | Description                                                                                                                                                                                                              |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **`-L`, `--logical`**  | Instructs **`pwd`** to output the **`$PWD`** [environment variable](https://phoenixnap.com/kb/linux-set-environment-variable) contents, including symbolic links. If no option is specified, **`pwd`** assumes **`-L`**. |
| **`-P`, `--physical`** | Prints the path to the [current directory](https://phoenixnap.com/glossary/what-is-a-directory). All the components are directory names, and symbolic links are resolved.                                                |
| **`--version`**        | Outputs the program version.                                                                                                                                                                                             |
| **`--help`**           | Displays the help message.                                                                                                                                                                                               |
