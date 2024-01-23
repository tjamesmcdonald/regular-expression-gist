# Regular Expressions

Regular Expressions are a way to define a search pattern without relying solely on literal characters. For example, instead of searching text for a specific phone number, you can search for all instances of phone numbers in a text that use similar patterns. This can be very useful in validating if an input matches what you are expecting to recieve (eg. email, password, etc.).

## Summary

In this example, we will look a regular expression for validating a password. If we want to require a password with atleast one letter, one number, and atleast eight characters, we can use the following regex(Regular Expression):
`/^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors define either the begining or end of the string. The `^` character denotes a string that starts with the characters that follow it, whereas the `$` character denotes a string that ends with the characters that came before it.

### Quantifiers

Quantifiers set limits on either the string you are searching for or its individual components. In our example, we use `{8,}` to ensure the string has atleast eight characters.

### Grouping Constructs

In order to satisfy multiple conditions, we need to break-up the expression into multiple sections. We do this by encasing them in parenthesies. In our example,
`(?=.*[A-Za-z])` and `(?=.*\d)` are separate subexpressions, the former checking for letters and the latter checking for numbers.

### Bracket Expressions

Anything inside a closed set of square breackets [] is considered a Bracket Expression. These expressions indicate a range of characters to be included in the search. For example, `[a-z]` will include all lowercase letters between a and z, since regular expressions are case sensitive. Bracket Expressions can also include special characters or numbers eg. `[0-9]` or `[-]`. These expressions can be combind to expand the search. For example, `[a-zA-Z0-9]` will include all letters and numbers in the search pattern.

### Character Classes

Character classes are a preset set of characters, providing a shorter way of writing a Regular Expression than using brack Expressions. In our example, the `/d` in `(?=.*\d)` is a shorthand version of `[0-9]`

### The OR Operator

The OR Operator (`|`), is not used in our exaple, but can be used to apply the same logic as found in Bracket Expressions. Eg. the expression `(1|2|3)` is equivalent to `[123]`.

### Flags

While not used in this example, flags can be used to assign additional limits to the Regular Expression. These flags are placed at the end of the expression, after the final `/`. Some common flags are: `g` for a global search, `i` for a case-insensitive search and `m`for a multi-line search.

### Character Escapes

Character Escapes prevent the regex from interpreting a character as a litteral character. For example if you wish to use a character class, as we did in the numerical subexpression `(?=.*\d)`, you must include the `\` before the `d`, or it will read the `d` as its literal lowercase letter.

## Author

Anthony McDonald  
My Github Profile: https://github.com/tjamesmcdonald
