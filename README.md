# Specific BASH Reference
Specifically for a subject I'm taking currently    
> Mainly serving as a reminder and reference for the specific commands they want us to be working with
> This is for my reference, substitute the inputs as necessary for your use-case.  

## Data processing

Regex for one or more whitespaces: `\s\+`  
Vim substitution (global): `%s/word/replace/g`  
Alphabetical ordering: `sort` `-o` for output file    

Un-endorsed solution for column printing: `awk '{print $1}'`  
Endorsed solution for column printing: `cut -f 1 -d "delimiter"`

#### Grep for files
`grep -l "pattern" /filepath/*` remember the wildcard, otherwise things don't work right  
Also remember: printing echoing grep results in removing newline characters.  

### RegEx reference :)
* `^`, `$` - carat and the dollar sign match the beginning and end of a line, respectively;
* \<, \> - the beginning and end of a word;
* `.` - full-stop matches any character.
* `string1\|string2` - matches either the text string1 or the text string2
* `[abc]` - matches any character that is one of "a" or "b" or "c"
* `[^abc]` - matches any character that is NOT one of "a" or "b" or "c"
* `[a-z]`, `[A-Z]`, `[0-9]` - matches a lowercase character, an uppercase character, a digit, respectively
* `*`, `\+` - * matches zero or more of the previous thing. \+ matches 1 or more of the previous thing.
