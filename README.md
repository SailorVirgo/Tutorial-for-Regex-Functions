# Regex Tutorial: Matching an Email

## Introduction
This tutorial explains how a specific regular expression, or regex, functions by breaking down each part of the expression and describing what it does. The regex we will be exploring is used to match a valid email address.

## Summary
The regex for matching an email address is: /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

This regex ensures that an email address has a proper format with an alphanumeric username, an @ symbol, a domain name, and a top-level domain.

## Table of Contents
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Escaping](#escaping)
- [Conclusion](#conclusion)
- [About the Author](#about-the-author)

## Anchors
Anchors are used to match the position before or after characters.
### `^` and `$`
- `^` asserts the position at the start of a string.
- `$` asserts the position at the end of a string.

In the regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the `^` ensures that the string starts with the username part and the `$` ensures it ends after the top-level domain. These anchors make sure the entire string is checked for the email format, not just a part of it.

## Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match.
### `+`
- `+` matches 1 or more of the preceding token.

In our regex, `([a-z0-9_\.-]+)` ensures that the username part contains one or more alphanumeric characters, dots, underscores, or hyphens. This means the username must have at least one of these characters, but there is no upper limit.

## Character Classes
Character classes match any one of a set of characters.
### `[a-z0-9_\.-]`
- Matches any lowercase letter (`a-z`), digit (`0-9`), underscore (`_`), dot (`.`), or hyphen (`-`).

Used in the username and domain parts of our regex, `[a-z0-9_\.-]` allows these characters to appear in the username and domain, making them flexible and capable of matching typical email address patterns.

## Grouping and Capturing
Grouping allows parts of a regex to be treated as a single unit.
### `()`
- `()` groups parts of the regex together and captures the matched substring.

Our regex has three capturing groups:
1. `([a-z0-9_\.-]+)` for the username.
2. `([\da-z\.-]+)` for the domain.
3. `([a-z\.]{2,6})` for the top-level domain.

These groups allow us to extract the username, domain, and top-level domain separately if needed.

## Bracket Expressions
Bracket expressions specify a set of characters to match.
### `[a-z\.]{2,6}`
- Matches between 2 and 6 lowercase letters or dots.

This part ensures the top-level domain (e.g., `.com`, `.org`, `.net`) is between 2 and 6 characters long. It can include only lowercase letters and dots, which covers most common top-level domains.

## Greedy and Lazy Match
### Greedy `*`, `+`, `{n,}`
- Greedy quantifiers match as much as possible.

Our regex uses greedy quantifiers like `+` to match as many characters as possible that fit the pattern. For example, `([a-z0-9_\.-]+)` will match the longest sequence of alphanumeric characters, dots, underscores, or hyphens it can find.

## Escaping
Escaping special characters allows them to be treated as literal characters.
### `\.`
- Matches a literal dot.

In our regex, `\.` is used to match the dots in email addresses, such as in the domain and top-level domain parts. Without the escape character (`\`), the dot would be treated as a wildcard character, matching any character.

## Conclusion
This regex effectively matches a properly formatted email address by using various components such as anchors, quantifiers, character classes, grouping, and escaping. By breaking down the regex, we can see how each part contributes to validating an email address.

## About the Author
This tutorial was written by Eric Casanova , a web development student passionate about coding and sharing knowledge. You can find more of my work on GitHub: [SailorVirgo](https://github.com/SailorVirgo).

