# Regular Expressions (Regex) Tutorial: Email Validation

Welcome to my tutorial on understanding regular expression (regex)! In this tutorial, I will explain regex, what it does, and how to use it to validate an email.

## Summary

Below is the regex I'll be explaining:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This regex checks whether a given string matches the format of a standard email address. I'll break down each section of our regex and explain what it does.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Author](#author)

## Regex Components

### Anchors

There are two anchors in regex: `^` and `$`. These anchors are used to define the start and end of a line or string.

- `^` indicates the beginning of the string
- `$` indicates the end of the string

### Quantifiers

Quantifiers define the rules for the number of characters allowed in specific parts of the email address. Our regex has a couple different quantifiers:

- `+` specifies that the element in front of the + should occur one more more times. In our regex example, it applies to `[a-z0-9_\.-]` and `[\da-z\.-]`. This allows one or more lowercase letters, numbers, underscores, periods, and hyphens in the email.
- `{2,6}` specifies that the element in front of the {2,6} should occur a minimum of 2 times and a maximum of 6 times. It applies to `[a-z\.]`. This allows 2-6 lowercase letters or periods.

### OR Operator

The OR operator (`|`) is used to match either the expression on its left or right. For example, an expression of `[a|b|c]` means the expression can contain a or b or c, but it doesn't have to be all of them together. Our regex doesn't have an OR operator.

### Character Classes

Character classes are used to define a set of characters. Our regex has two character classes:

- `[a-z0-9_\.-]` matches any lowercase letter, number, underscore, period, or hyphen.
- `[\da-z\.-]` matches any number, lowercase letter, period, or hyphen.

Note: `\d` is equivalent to the `[0-9]` expression.

### Flags

Flags are additional modifiers used at the end of expressions. A few examples of these include:

- `i` stands for "Case-Insensitive". This indicates that uppercase and lowercase doesn't make a difference while attempting a match in a string.
- `g` stands for "Global". This returns all iinstances of a search parameter.
- `m` stands for "Multi-line". This helps find the match if the input is multiple lines.

Our email regex doesn't use flags, but for the sake of an example, using the `i` flag would look like this:

- `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/i`

### Grouping and Capturing

Grouping and Capturing helps by putting a string into different sections that each have their own specific requirements. Our regex example groups the requirements into three different sections:

- `([a-z0-9_\.-]+)` is for the username of the email address
- `([\da-z\.-]+)` is for the domain name (gmail, yahoo, outlook, etc.)
- `([a-z\.]{2,6})` is for the top-level domain (.com, .org, .edu, .gov, etc.)

### Bracket Expressions

Bracket expressions are where we store the set of rules for certain characters in our search. For example, our regex uses `[a-z\.]` to match any lowercase letter or period in the top-level domain.

### Greedy and Lazy Match

Greedy matching means the regex will match as many instances as possible. Lazy matching means the regex will match the least amount of instances possible. 

- `*` matches zero or more times
- `+` matches one or more times
- `?` matches zero or one time

### Boundaries

Boundaries, like anchors, are used at the beginning and end of a string. The `/b` is a word boundary which matches at the start or end of a word. Our regex example doesn't use any word boundaries.

### Back-references

Back-references allow matching a previously matched group again in the regex. Our regex example doesn't include any back-references.

### Look-ahead and Look-behind

Look-ahead adds a condition for what follows. Look-behind adds a condition for what's behind. Our regex example doesn't use look-ahead or look-behind.

## Author

This tutorial was written by [Blake Edwards](https://github.com/blakeedwards3) for the UNCC Coding Bootcamp

## References

- https://cheatography.com/davechild/cheat-sheets/regular-expressions/
- https://stackoverflow.com/questions/2301285/what-do-lazy-and-greedy-mean-in-the-context-of-regular-expressions
- https://www.regular-expressions.info/wordboundaries.html