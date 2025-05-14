# Specific BASH Reference
Specifically for a subject I'm taking currently    
> Mainly serving as a reminder and reference for the specific commands they want us to be working with
> This is for my reference and some classmates, substitute the inputs as necessary for your use-case.  

## `ls`  

`-1` seperate by lines  
`-a` all, including `.` & `..`  
`-R` recursive (they don't teach this, but it's a faster solution to some problems)  

**To get `.` & `..` plus hidden files:**  
`ls  path/ | grep -e "^\." ` - (remember the escape character on the period)   

**To get full filepath, use a wildcard:**  
`ls /path/*`  

## Perms
```
r  4
w  2
x  1

chmod [ugo ][+-] [rwx]
```

## Variables & Wildcards
In addition to `$<x>` for arguments:  
* `$#` - number of arguments  
* `$?` - return code of previous command (0 = success)  

### Wildcards
* `*` - 0 or more of anything
* `?` - matches any single char
* `[]` - matches range of chars
* `{}` - groups patterns, seperated by `,`
* `[!]` - negative match
* `\` - escape char

## Redirection
```
STDIN 0
STDOUT 1
STDERR 2

>&
```

## Arithmetic 
`$(($a <operation> $b))`  

## Logic & Flow control
Arithmetic symbols are used for strings.  
For numeric logic:
* `-eq` `-nq`
* `-gt` `-ge`
* `-lt` `-le`
`[[ ]]` - for logic
`(( ))` - for math


## Data processing

Regex for one or more whitespaces: `\s\+`  
Vim substitution (global): `%s/word/replace/g`  
Alphabetical ordering: `sort` `-o` for output file    

Un-endorsed solution for column printing: `awk '{print $1}'`  
Endorsed solution for column printing: `cut -f 1 -d "delimiter"`

### Regarding `cut`
It has a problem with variable whitespace delimiters, so cutting a column except the first one doesn't work, use RegEx & substitution first and then the delimiter can be a comma or something.  
The simplest way I used to fulfill their requirements is `grep` piped into `cut`  

### Regarding `grep`
**For words**  
Be mindful of whether you're using the `-w` flag 😂  

**For regex**  
`-e` or `-E`  

**For files**  
`grep -l "pattern" /filepath/*` remember the wildcard, otherwise things don't work right  
Also remember: echoing grep results in removing newline characters.  

**Case insensitive**  
`grep -i`  

**Inverted match**  
`grep -v`  

### RegEx reference :)

Note: for actual patterns, they want us to nest `grep` commands and use `grep -v` instad of building a respectable expression.  

* `^`, `$` - carat and the dollar sign match the beginning and end of a line, respectively;
* \<, \> - the beginning and end of a word;
* `.` - full-stop matches any character.
* `string1\|string2` - matches either the text string1 or the text string2
* `[abc]` - matches any character that is one of "a" or "b" or "c"
* `[^abc]` - matches any character that is NOT one of "a" or "b" or "c"
* `[a-z]`, `[A-Z]`, `[0-9]` - matches a lowercase character, an uppercase character, a digit, respectively
* `*`, `\+` - * matches zero or more of the previous thing. \+ matches 1 or more of the previous thing.

## Misc
**Wordcount**
Pipe into `wc` to prevent filename being displayed.  
Bytes, characters, lines or words can be counted.
