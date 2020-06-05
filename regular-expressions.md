# Regular expressions

## Functions

* matching - matches from the beginning of a string  
* searching - searches for the pattern anywhere in the starting and returns the first occurrence  

## Comments

`(?#)` -&gt; `(?#comment)`

## Metacharacters:

```text
 .  ^  *  +  ?  {  }  [  ]  \  |  (  )
```

## Matching

`[ ]` - set of characters to match -&gt; `[abc]`  
`-` - range of characters -&gt; `[a-c]`  
`^` - complement of characters -&gt; `[^5]`  
`\` - remove special meaning -&gt; `\[` or `\^` or `\\`

`\w` - all alphanumeric characters -&gt; `[a-zA-Z0-9_]`  
`\W` - except all alphanumeric characters -&gt; `[^a-zA-Z0-9_]`  
`\d` - all numeric characters -&gt; `[0-9]`  
`\D` - except all numeric characters -&gt; `[^0-9]`  
`\s` - all whitespace characters -&gt; `[ \t\n\r\f\v]`  
`\S` - except all whitespace characters -&gt; `[^ \t\n\r\f\v]`  
`re.DOTALL` or `.` -&gt; any character  
`.` matches any character, to match `.` character, escape with `\` -&gt; `\.`

`|` - or operator  
`^` - matches at the beginning of a line and following a \n  
`$` - matches at the end of a line  
`\c` - matches any special character -&gt; `\\ \*` `\A` - only matches at the start of a string  
`\Z` - only matches at the end of a string  
`\b` - matches only at the beginning and end of a word \(alphanumeric\)  
`\B` - matches not at a word boundary

## Repeating

`*` - matches characters 0 or more times instead of once  
`ca*t` - ct, cat, caat, caaat, ...

`+` - matches 1 or more times  
`ca+t` - cat, caat, caaat, ...

`?` - 0 or 1 time  
`ca?t` - ct, cat

`{n}` - match exactly n occurrences - n - decimal integer  
`ca{3}t` - caaat

`{m,n}` - at least m to at most n - m,n - decimal integers  
`ca{1,3}t` - cat, caat, caaat

`(*|+|?|{})?` - non-greedy \(consume less characters as possible\) versions of symbols \(\*,+,?,{}\) -&gt; `[a-c]*?`

## Grouping

`( )` - group expressions  
`\N` - match Nth subgroup `(?iLmsux)` - embed flags within regex  
`(?:)` - non saved groups  
`(?P<name>)` - identify group with name  
`(?P=name)` - match group by name  
`(?g<name>)` - retrieve named groups saved by ?P

`(?=)` - matches if comes next, positive lookahead assertion -&gt; `(?=.com)` `(?!)` - matches if doesn't come next, negative lookahead assertion -&gt; `(?!for)`  
`(?<=)` - matches if comes prior, positive lookbehind assertion -&gt; `(?<=def)`  
`(?<!)` - matches if doesn't come prior, negative lookbehind assertion -&gt; `(?<!.net)` `(?(id/name)Y|N)` - conditional or ternary match, N is optional -&gt; `(?(1)y|x)`

## Compilation Flags

`ASCII`, `A` - match only ascii with `\w`, `\b`, `\s`, `\d`  
`DOTALL`, `S` - any character  
`IGNORECASE`, `I` - case-insensitive matches  
`LOCALE`, `L` - Include locale based characters  
`MULTILINE`, `M` - multiline matching  
`VERBOSE`, `X` - verbose regex, including comments  
`UNICODE`, `U` - match unicode characters

## Python - re

### Methods

* `compile(pattern, flags=0)` - return regex object
* `match(pattern, string, flags=0)` - return match object or None
* `group(num=0)` - return matched string
* `groups()` - return all matched subgroups in tuple
* `groupdict()` - return all matched subgroups in a dictionary \(key-names\)
* `start()` - return starting index
* `end()` - return ending index
* `span()` - return tuple of starting and ending index
* `search(pattern, string, flags=0)` - return match object or None
* `findall(pattern, string[,flags])` - returns list of matches
* `finditer(pattern, string[,flags])` - returns iterator match object
* `split(pattern, string, max=0)` - split string according to pattern max times, return matches
* `sub(pattern, repl, string, count=0)` - replace pattern with repl in string
* `subn(pattern, repl, string, count=0)` - as sub and return total number of substitutions  
* `purge()` - purge compiled cache

### Compilation flags

\(multiple flags in methods - `|`\)

* `re.I` - IGNORECASE
* `re.M` - MULTILINE  
* `re.S` - DOTALL  
* `re.X` - VERBOSE  
* `re.L` - LOCALE  
* `re.U` - UNICODE  

## Javascript - regex

```text
regex = \...\
```

### Methods

* test - `regex.test(string)` - true or false
* match - `string.match(regex)` - extract matches
* replace - `string.replace(regex, replacestring)` - find and replace

### Flags

```text
regex = \...\flags
```

* i - ignorecase
* g - global - match more than once

## References

1. [https://docs.python.org/3/howto/regex.html](https://docs.python.org/3/howto/regex.html)
2. Wesley J. Chun, Core Python Programming 3rd edition, Chapter 1
3. [Practice in HackerRank](https://www.hackerrank.com/domains/regex)
4. [Practice in FreeCodeCamp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/)

