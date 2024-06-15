---
description: jq linux command cheatsheet by Thamizhiniyan C S
---

# jq

## Introduction

jq is a tool for processing JSON inputs, applying the given filter to its JSON text inputs and producing the filter's results as JSON on standard output.

***

## Syntax

`jq [options...] filter [files...]`

***

## Installation

For Installing on a Debian based OS or Ubuntu use the following command:

```bash
sudo apt-get install jq
```

***

## Important Flags

| Flag              | Description                                                 |
| ----------------- | ----------------------------------------------------------- |
| `-c`              | Compact instead of pretty-printed output.                   |
| `-n`              | Use \`null\` as the single input value.                     |
| `-e`              | Set the exit status code based on the output.               |
| `-s`              | Read (slurp) all inputs into an array; apply filter to it.  |
| `-r`              | Output raw strings, not JSON texts. (prints without quotes) |
| `-R`              | Read raw strings, not JSON texts.                           |
| `-C`              | Colorize JSON.                                              |
| `-M`              | Monochrome (don't colorize JSON).                           |
| `-S`              | Sort keys of objects on output.                             |
| `--tab`           | Use tabs for indentation.                                   |
| `--arg a v`       | Set variable $a to value .                                  |
| `--argjson a v`   | Set variable $a to JSON value .                             |
| `--slurpfile a f` | Set variable $a to an array of JSON texts read from .       |
| `--rawfile a f`   | Set variable $a to a string consisting of the contents of . |
| `--args`          | Remaining arguments are string arguments, not files.        |
| `--jsonargs`      | Remaining arguments are JSON arguments, not files.          |
| `--`              | Terminates argument processing.                             |

***

## jq Filters

Source: [https://gist.github.com/olih/f7437fb6962fb3ee9fe95bda8d2c8fa4](https://gist.github.com/olih/f7437fb6962fb3ee9fe95bda8d2c8fa4)

### Basic concepts

The syntax for jq is pretty coherent:

<table><thead><tr><th width="207">Syntax</th><th>Description</th></tr></thead><tbody><tr><td><code>,</code></td><td>Filters separated by a comma will produce multiple independent outputs</td></tr><tr><td><code>?</code></td><td>Will ignores error if the type is unexpected</td></tr><tr><td><code>[]</code></td><td>Array construction</td></tr><tr><td><code>{}</code></td><td>Object construction</td></tr><tr><td><code>+</code></td><td>Concatenate or Add</td></tr><tr><td><code>-</code></td><td>Difference of sets or Substract</td></tr><tr><td><code>length</code></td><td>Size of selected element</td></tr><tr><td><code>|</code></td><td>Pipes are used to chain commands in a similar fashion than bash</td></tr></tbody></table>

### Dealing with json objects

| Description                |                 Command                 |
| -------------------------- | :-------------------------------------: |
| Display all keys           |               `jq 'keys'`               |
| Adds + 1 to all items      |          `jq 'map_values(.+1)'`         |
| Delete a key               |             `jq 'del(.foo)'`            |
| Convert an object to array | `to_entries &#124; map([.key, .value])` |

### Dealing with fields

| Description            |             Command            |
| ---------------------- | :----------------------------: |
| Concatenate two fields | `fieldNew=.field1+' '+.field2` |

### Dealing with json arrays

#### Slicing and Filtering

<table><thead><tr><th width="306">Description</th><th>Command</th></tr></thead><tbody><tr><td>All</td><td><code>jq .[]</code></td></tr><tr><td>First</td><td><code>jq '.[0]'</code></td></tr><tr><td>Range</td><td><code>jq '.[2:4]'</code></td></tr><tr><td>First 3</td><td><code>jq '.[:3]'</code></td></tr><tr><td>Last 2</td><td><code>jq '.[-2:]'</code></td></tr><tr><td>Before Last</td><td><code>jq '.[-2]'</code></td></tr><tr><td>Select array of int by value</td><td><code>jq 'map(select(. >= 2))'</code></td></tr><tr><td>Select array of objects by value</td><td><code>jq '.[] | select(.id == "second")'</code></td></tr><tr><td>Select by type</td><td><code>jq '.[] | numbers'</code>  with type been <code>arrays</code>, <code>objects</code>, <code>iterables</code>, <code>booleans</code>, <code>numbers</code>, <code>normals</code>, <code>finites</code>, <code>strings</code>, <code>nulls</code>, <code>values</code>, <code>scalars</code></td></tr></tbody></table>

#### Mapping and Transforming

| Description                          | Command                                                               |
| ------------------------------------ | --------------------------------------------------------------------- |
| Add + 1 to all items                 | `jq 'map(.+1)'`                                                       |
| Delete 2 items                       | `jq 'del(.[1, 2])'`                                                   |
| Concatenate arrays                   | `jq 'add'`                                                            |
| Flatten an array                     | `jq 'flatten'`                                                        |
| Create a range of numbers            | `jq '[range(2;4)]'`                                                   |
| Display the type of each item        | `jq 'map(type)'`                                                      |
| Sort an array of basic type          | `jq 'sort'`                                                           |
| Sort an array of objects             | `jq 'sort_by(.foo)'`                                                  |
| Group by a key - opposite to flatten | `jq 'group_by(.foo)'`                                                 |
| Minimun value of an array            | `jq 'min'` .See also min, max, min\_by(path\_exp), max\_by(path\_exp) |
| Remove duplicates                    | `jq 'unique'` or `jq 'unique_by(.foo)'` or `jq 'unique_by(length)'`   |
| Reverse an array                     | `jq 'reverse'`                                                        |

***

## Examples

In the given examples, the following JSON data is used which is stored in a file "json.json".

```
[{"layout":"en-gb","textType":"random","timeStamp":"2023-05-11T10:15:20.000Z","length":145,"time":31025,"errors":5,"speed":193.4567820395721,"histogram":[{"codePoint":32,"hitCount":20,"missCount":1,"timeToType":257},{"codePoint":101,"hitCount":29,"missCount":2,"timeToType":198},{"codePoint":105,"hitCount":18,"missCount":0,"timeToType":215},{"codePoint":108,"hitCount":10,"missCount":1,"timeToType":180},{"codePoint":110,"hitCount":12,"missCount":0,"timeToType":172},{"codePoint":114,"hitCount":7,"missCount":3,"timeToType":327},{"codePoint":116,"hitCount":33,"missCount":1,"timeToType":305}]},{"layout":"en-us","textType":"auto","timeStamp":"2024-01-15T08:25:35.000Z","length":132,"time":28567,"errors":3,"speed":204.2876359102458,"histogram":[{"codePoint":32,"hitCount":19,"missCount":1,"timeToType":263},{"codePoint":101,"hitCount":31,"missCount":0,"timeToType":210},{"codePoint":105,"hitCount":22,"missCount":1,"timeToType":225},{"codePoint":108,"hitCount":14,"missCount":0,"timeToType":190},{"codePoint":110,"hitCount":15,"missCount":0,"timeToType":180},{"codePoint":114,"hitCount":9,"missCount":2,"timeToType":335},{"codePoint":116,"hitCount":34,"missCount":1,"timeToType":315}]},{"layout":"fr-fr","textType":"generated","timeStamp":"2023-07-22T14:45:50.000Z","length":150,"time":32015,"errors":6,"speed":180.9324721938471,"histogram":[{"codePoint":32,"hitCount":21,"missCount":2,"timeToType":269},{"codePoint":101,"hitCount":28,"missCount":1,"timeToType":205},{"codePoint":105,"hitCount":20,"missCount":0,"timeToType":230},{"codePoint":108,"hitCount":13,"missCount":1,"timeToType":185},{"codePoint":110,"hitCount":16,"missCount":0,"timeToType":178},{"codePoint":114,"hitCount":11,"missCount":2,"timeToType":345},{"codePoint":116,"hitCount":32,"missCount":2,"timeToType":325}]},{"layout":"de-de","textType":"random","timeStamp":"2023-03-11T16:35:40.000Z","length":120,"time":27890,"errors":4,"speed":198.4783292857362,"histogram":[{"codePoint":32,"hitCount":17,"missCount":1,"timeToType":250},{"codePoint":101,"hitCount":27,"missCount":0,"timeToType":207},{"codePoint":105,"hitCount":19,"missCount":1,"timeToType":218},{"codePoint":108,"hitCount":11,"missCount":0,"timeToType":182},{"codePoint":110,"hitCount":13,"missCount":0,"timeToType":176},{"codePoint":114,"hitCount":10,"missCount":3,"timeToType":338},{"codePoint":116,"hitCount":30,"missCount":1,"timeToType":310}]},{"layout":"es-es","textType":"generated","timeStamp":"2023-11-05T12:55:25.000Z","length":125,"time":29235,"errors":2,"speed":205.6798234710598,"histogram":[{"codePoint":32,"hitCount":22,"missCount":2,"timeToType":255},{"codePoint":101,"hitCount":26,"missCount":1,"timeToType":215},{"codePoint":105,"hitCount":21,"missCount":0,"timeToType":228},{"codePoint":108,"hitCount":15,"missCount":0,"timeToType":188},{"codePoint":110,"hitCount":18,"missCount":1,"timeToType":170},{"codePoint":114,"hitCount":12,"missCount":2,"timeToType":350},{"codePoint":116,"hitCount":29,"missCount":1,"timeToType":300}]}]
```

### Pretty Printing JSON

| Command                                                                                                       | Description                                          |
| ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat json.json | jq "."
</code></pre>  | Using jq along with cat for Pretty printing the JSON |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.' json.json
</code></pre>        | Output a JSON file, in pretty-print format           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq "." &#x3C; json.json
</code></pre> | To pretty print the json                             |

***

### Extracting Keys

| Command                                                                                                             | Description                   |
| ------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq keys json.json
</code></pre>             | To extract all keys from json |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[0]' json.json | jq keys
</code></pre> | To extract all keys from json |

***

### Array Manipulation

| Command                                                                                                                   | Description                                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[]' json.json
</code></pre>                  | Output all elements from arrays (or all key-value pairs from objects) in a JSON file                                                                                                                                                                                               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq -cM ".[]" json.json | jq --slurp
</code></pre> | Read JSON objects from a file into an array, and output it \[ Note: In our case the given the given JSON data is already an array of JSON objects. Thus, first I extracted the JSON objects from the array and piped it again to jq to use -slurp, for the sake of demonstration ] |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[] | .layout' json.json
</code></pre>        | Extract as stream of values instead of a list (array)                                                                                                                                                                                                                              |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[] | length' json.json
</code></pre>         | To count elements                                                                                                                                                                                                                                                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '[range(2;4)]' json.json
</code></pre>         | Create a range of numbers                                                                                                                                                                                                                                                          |

***

### Array Indexing

| Command                                                                                                          | Description                                                         |
| ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[0]' json.json
</code></pre>        | To access first list item                                           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[0]' json.json
</code></pre>        | Output the first element in a JSON file                             |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[0].layout' json.json
</code></pre> | Output the value of a given key of the first element in a JSON file |

***

### Array Slicing

| Command                                                                                                                     | Description                                                                                          |
| --------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[1:4] | map(.layout)' json.json
</code></pre>  | Slicing the elements from 1 to 4 ( i.e, 1,2,3 ) and printing the value of the layout key as an array |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[1:4] | .[] | .layout' json.json
</code></pre> | Slicing the elements from 1 to 4 ( i.e, 1,2,3 ) and printing the value of the layout key as stream   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[2:4]' json.json
</code></pre>                 | Slicing example 1                                                                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[:3]' json.json
</code></pre>                  | Slicing example 2                                                                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[-2:]' json.json
</code></pre>                 | Slicing example 3                                                                                    |

***

### Filtering and Manipulating Data

| Command                                                                                                                               | Description                                          |
| ------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'add' json.json
</code></pre>                              | Concatenate arrays                                   |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'del(.[1, 2])' json.json
</code></pre>                     | Delete 2 items                                       |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[] | select(.layout == "en-gb")' json.json
</code></pre> | Only print records where given field matches a value |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'group_by(.textType)' json.json
</code></pre>              | Group by a key - opposite to flatten                 |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'min' json.json
</code></pre>                              | Minimum value of an array                            |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'reverse' json.json
</code></pre>                          | Reverse an array                                     |

***

### Mapping

| Command                                                                                                                                 | Description                                                    |
| --------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'map(type)' json.json
</code></pre>                          | Display the type of each item                                  |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'map(.layout)' json.json
</code></pre>                       | Output the value of a given key of each element in a JSON file |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'map({ layout, textType })' json.json
</code></pre>          | Dictionary subset shorthand                                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'map(select(.textType == "random"))' json.json
</code></pre> | Filter a list of objects                                       |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'map(.length + 1)' json.json
</code></pre>                   | Add + 1 to all items                                           |

***

### Sorting

| Command                                                                                                                     | Description                 |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'sort' json.json
</code></pre>                   | Sort an array of basic type |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'sort_by(.length)' json.json
</code></pre>       | Sort an array of objects    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq --slurp '. | sort | .[]' json.json
</code></pre> | Sort lines of a file        |

***

### Unique

| Command                                                                                                                 | Description                 |
| ----------------------------------------------------------------------------------------------------------------------- | --------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'unique' json.json
</code></pre>             | Remove duplicates           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'unique_by(.layout)' json.json
</code></pre> | Remove duplicates by key    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'unique_by(length)' json.json
</code></pre>  | Remove duplicates by length |

***

### Converting / Parsing / Serializing

| Command                                                                                                                                 | Description      |
| --------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'flatten' json.json
</code></pre>                            | Flatten an array |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'with_entries(.value |= fromjson)' --sort-keys
</code></pre> | Parsing json     |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq 'with_entries(.value |= tojson)' --sort-keys
</code></pre>   | Serializing json |

***

### Converting to CSV

| Command                                                                                                                                                                                                                                                                              | Description                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[] | [.layout, .length] | @csv' -r json.json
</code></pre>                                                                                                                                              | Converting to csv                                                                                         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq -r '.[] | [.layout, .textType, .timeStamp, .length, .time, .errors, .speed] | @csv' json.json
</code></pre>                                                                                               | This command takes each object in the JSON array, extracts the specified fields, and formats them as CSV. |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq -r '.[] | [.layout, .textType, .timeStamp, .length, .time, .errors, .speed, (.histogram | map([.codePoint, .hitCount, .missCount, .timeToType] | join(",")) | join(";"))] | @csv' json.json
</code></pre> | Same as the previous command but also includes histogram (nested array) data                              |

***

### Formatting

| Command                                                                                                                                 | Description                                   |
| --------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[] | {layout, length}' json.json
</code></pre>             | Print only selected fields                    |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq '.[] | {layout, length} | join(" ")' json.json
</code></pre> | Print selected fields as text instead of json |

***

### URL Encoding

| Command                                                                                                      | Description         |
| ------------------------------------------------------------------------------------------------------------ | ------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">jq -sRr @uri json.json
</code></pre> | URL Encode the data |

***

### Exporting Data / Environment Variables

| Command                                                                                                                                                                                         | Description                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">export layout="a shell variable or an env" &#x26;&#x26; jq -n --arg layout "$layout" '{"layout":$layout}'
</code></pre> | To create proper JSON from a shell script and properly escape variables |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">export $(jq -r '@sh "FOO=\(.foo) BAZ=\(.baz)"')
</code></pre>                                                           | To fill environment variables from JSON object key                      |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">export $(jq -r '.[0] | "LAYOUT=\(.layout) LENGTH=\(.length)"' json.json)
</code></pre>                                  | To fill environment variables from the JSON file                        |

***

### With cat Command

| Command                                                                                                                                                                              | Description                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------- |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat json.json | jq --from-file script.jq
</code></pre>                                                       | Execute a specific script         |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat path/to/file.json | jq --arg "name1" "value1" --arg "name2" "value2" ... '. + $ARGS.named'
</code></pre> | Pass specific arguments           |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat path/to/file.json | jq '.key1, .key2, ...'
</code></pre>                                                 | Print specific keys               |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat path/to/file.json | jq '.[index1], .[index2], ...'
</code></pre>                                         | Print specific array items        |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat path/to/file.json | jq '.[]
</code></pre>                                                                | Print all array items/object keys |
| <pre class="language-bash" data-overflow="wrap"><code class="lang-bash">cat path/to/file.json | jq '. +|- {"key1": "value1", "key2": "value2", ...}'
</code></pre>                   | Add/remove specific keys          |
