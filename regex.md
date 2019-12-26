# Regular expressions

## Functions
* matching  
* repeated matching

## Metacharacters:
` . ^ * + ? { } [ ] \ | ( ) `

## Matching
`[ ]` -> set of characters to match -> `[abc]`  
 `-`  -> range of characters -> `[a-c]`  
 `^`  -> complement of characters -> `[^5]`  
 `\`  -> remove special meaning -> `\[` or `\^` or `\\`  
 `\w` -> all alphanumeric characters -> `[a-zA-Z0-9_]`  
 `\W` -> except all alphanumeric characters -> `[^a-zA-Z0-9_]`  
 `\d` -> all numeric characters -> `[0-9]`  
 `\D` -> except all numeric characters -> `[^0-9]`  
 `\s` -> all whitespace characters -> `[ \t\n\r\f\v]`   
 `\S` -> except all whitespace characters -> `[^ \t\n\r\f\v]`  
`re.DOTALL` or `.` -> any character  
. matches any character, to match `.`, escape with `\` as `\.`

`|`  -> or operator  
`^`  -> matches at the beginning of a line and following a \n  
`$`  -> matches at the end of a line  
`\A` -> only matches at the start of a string  
`\Z` -> only matches at the end of a string  
`\b` -> matches only at the beginning and end of a word (alphanumeric)  
`\B` -> matches not at a word boundary

## Repeating
`*` -> matches characters 0 or more times instead of once  
`ca*t` - ct, cat, caat, caaat, ...

`+` -> matches 1 or more times  
`ca+t` - cat, caat, caaat, ...

`?` -> 0 or 1 time  
`ca?t` - ct, cat

`{m,n}` - atleast m to atmost n - m,n - decimal integers  
`ca{1,3}t` - cat, caat, caaat  

## Grouping
`( )` -> group expressions  

## Compilation Flags
`ASCII`, `A` - match only ascii with `\w`, `\b`, `\s`, `\d`  
`DOTALL`, `S` - any character  
`IGNORECASE`, `I` - case-insensitive matches  
`LOCALE`, `L` - Include locale based characters  
`MULTILINE`, `M` - multiline matching  
`VERBOSE`, `X` - verbose regex, including comments  

## Python - re
https://docs.python.org/3/howto/regex.html

### Methods
* match()
  * group() - matched string
  * start() - starting index
  * end() - ending index
  * span() - tuple of starting and ending index


* search()
* findall() - returns list
* finditer() - returns iterator
* sub()

## Javascript - regex

```
regex = \...\
```

### Methods
* test - `regex.test(string)` - true or false
* match - `string.match(regex)` - extract matches
* replace - `string.replace(regex, replacestring)` - find and replace

### Flags
```
regex = \...\flags
```
* i - ignorecase
* g - global - match more than once
