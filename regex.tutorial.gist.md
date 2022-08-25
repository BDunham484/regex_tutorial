# Matching an Email Regex Tutorial

In this tutorial I'll outline how the specific parts of a regular expression apply to matching an email.

## Summary

A **regular expression** or **regex** for short is a series of characters that defines a specific search pattern.  The following regex defines the search for an email address. 

```js
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Below I'll pick apart the specific components of this regex and explain how they function in searching for an email address
___
## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components
_________


### Anchors: `^` and `$`

These characters start and end a string respectively.  They indicate that whatever is between them is what will need to be matched in order to complete the search.  

/`^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$`/
___

### Quantifiers: `+ and {x, y}`
`{x, y}`
In this case, these quantifiers indicate that we want to find an expression between 2 and 6 in length.
    
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]`{2,6}`)$/

`+`
Indicates we are looking for a match of characters to the left of this quantifier.  The character closest to it on the left however, there may be one or more of.

([a-z0-9_\.-]`+`)

Here it matches any combination of lowercase characters, numbers, periods, underscores or dashes.  

___

### OR Operator: `[]`

This indicates that we are matching one or another character given between the OR Operator brackets.  As seen below:

/^(`[a-z0-9_\.-]`+)@(`[\da-z\.-]`+)\.(`[a-z\.]`{2,6})$/

`[a-z0-9_\.-]` - Matches any lowercase letters, numbers 0-9, underscores, periods or dashes<br>
`[\da-z\.-]` - Matches any single digit, lowercase letters, periods or dashes<br>
`[a-z\.]` - matches any lowercase letters and periods<br>

___

### Character Classes: `\.\d`
`\.`
This matches any periods given in an expression:

/^(`[a-z0-9_`\.`-]`+)@(`[\da-z`\.`-]`+)\.(`[a-z`\.`]`{2,6})$/

`\d`
This matches single characters that are digits from 0-9:

/^(`[a-z0-9_\.-]`+)@(`[`\d`a-z\.-]`+)\.(`[a-z\.]`{2,6})$/

___


### Grouping and Capturing: `()`

Parentheses capture all characters listed inside.  If there are more than one captured group they are stored in an array and can be accessed by their specific index.

/^`([a-z0-9_\.-]+)`@`([\da-z\.-]+)`\.`([a-z\.]{2,6})`$/

With our given regex there are three captured groups

___

### Bracket Expressions: `[]`

Matches a string of the given parameters within the brackets.

`[\da-z\.-]`

Above we see it matching any single digit with a combination of lowercase characters a-z, any jperiods and dashes
___

### Greedy Match: `+`

This is known as a 'greedy' quantifier.  It expands the match as far as it can through the provided text. 

/^([a-z0-9_\.-]`+`)@([\da-z\.-]`+`)\.([a-z\.]{2,6})$/

Because the line starts within a parentheses and ends witin a parentheses it captures almost the entire line rather than just between the parentheses where it is called. 

___

## Author

[Brad Dunham: A full stack developer ](https://www.github.com/BDunham484)



