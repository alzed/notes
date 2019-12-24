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
. matches any character, to match '.', escape with '\' as '\.'

`|`  -> or operator  
`^`  -> matches at the beginning of a line and following a \n  
`$`  -> matches at the end of a line  
`\A` -> only matches at the start of a string  
`\Z` -> only matches at the end of a string  
`\b` -> matches only at the beginning and end of a word (alphanumeric)  
`\B` -> matches not at a word boundary  
