# Module 17 Regex

This is the gist for the module 17 challenge.

## Summary

I will be describing the "Matching an Email" regex, or regular expression, as shown here: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
A matching email regex would be used to validate an email address. For example, if a user is filling out a form online or answering an inquirer prompt in a node.js program, this regex could be used to make sure they enter an email address when asked for one. Essentially, a regex is defining a search pattern.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components

### Anchors

Anchors match a position before, after or between characters. The caret, `^` matches the position before the first character in the string, and the dollar symbol, `$` matches after the last character of the string. So, like in the snippet above, the `^` and `$` basically contain the parameters of the regex.


### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present for a match to be found. So, for a regex that is meant to match an email address, you'd want to use the plus sign, +, operator. The + on it's own is known as a greedy operator, as it will match as many occurances as possible. In `[a-z0-9_\.-]+@` from our email matching regex, the expression will look for at least one or more instances of everything in the brackets: "lowercase a through z" and/or of "zero through nine" a period (the backslash lets the regex interpret the period as a literal period by "escaping" it), and a dash. After the + is the @ so it will stop this part of the search once it gets to the @.

The `{2,6}` at the end will looks for a range of 2-6 characters. Which works for an email address because they end in something like .com or .net which is between 2 and 6 characters long.

### OR Operator
NA for this regex.

### Character Classes

The `\d` used in the email matching regex is looking for any single digit. Since it is wrapped in brackets followed by the + sign, it can be one or more digits If it was just on its own it would only allow a single digit, or something like \d\d\d that would mean only three digits.

### Flags

The `/` is used to delimit the expression. And would come before the caret and after the dollar sign. After the closing `/` g = global search, i = case sensitive search, m = multi-line search, are some flags that may be used.

### Grouping and Capturing

Parenthases are used to group parts of the expression together. In `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`  the username is grouped, then the provider name is grouped, but between them is an @ symbol so nothing affecting those groups affects the @ symbol and the regex will just look for a single @ symbol between those two groups. 

### Bracket Expressions

Using brackets allows a regex to match specific characters in a range. So, `[a-z]` is not looking for a or - or z, but actually looking for any letters a through z. And in the brackets the "-" is not taken literally in the cases of a-z or 0-9. But after the \ to escape the period it is recognized as a literal "-".


### Greedy and Lazy Match

A greedy match will match as much as possible while the lazy match will try to match as little as possible. In matches in the email regex are greedy and will match as much as possible.

## Author
 #### <a href="https://www.github.com/hippobb">william Chow</a>