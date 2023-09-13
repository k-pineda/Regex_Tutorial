# Matching a URL - Explained

In this tutorial, we will break down and explain the regular expression `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`. This regex is designed to match URLs and can be used to validate and extract components of a URL such as the protocol, domain, and path. We will dissect each part of this expression to understand its purpose and functionality.
## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

This regular expression is used to match URLs and can be divided into several components. It starts with an optional protocol (http:// or https://), followed by a domain name, an optional path, and an optional trailing slash. The regex is designed to handle URLs with or without a protocol, www subdomains, and various domain extensions.

```javascript
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```

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

- `^` at the beginning of the regex asserts the start of the line.
- `$` at the end of the regex asserts the end of the line. This ensures that the entire string is matched, not just a part of it.

### Quantifiers

- `?` makes the preceding group `(https?:\/\/)` optional. It matches URLs with or without a protocol.

### Grouping Constructs

- `(https?:\/\/)` captures the protocol (http:// or https://) if it exists. The `?` after this group makes it optional.
- `([\da-z\.-]+)` captures the domain name, which can consist of letters, digits, dots, or hyphens. It can also include subdomains (e.g., www).
- `([a-z\.]{2,6})` captures the top-level domain (TLD), which consists of lowercase letters and dots. It allows for TLDs between 2 and 6 characters in length.
- `([\/\w \.-]*)*` captures an optional path, which can include letters, digits, slashes, dots, hyphens, and spaces. The `*` quantifier allows for zero or more path characters.
- `\/?$` captures an optional trailing slash at the end of the URL.

### Bracket Expressions

Bracket expressions are used within character classes:

- `[\da-z\.-]` matches any digit (`\d`), lowercase letter (`a-z`), dot (`.`), or hyphen (`-`).

### Character Classes

Character classes define sets of characters:

- `\d` matches any digit (0-9).
- `\w` matches any word character (letters, digits, or underscores).
- `\.` matches a literal dot.
- ` ` (space) matches a literal space.

### The OR Operator

- `http` matches the characters "http" literally.
- `s?` matches the character "s" zero or one time, making "https" optional.

### Flags

This regular expression does not use any flags such as case-insensitivity.

### Character Escapes

There are no character escapes in this regular expression.

## Author

This tutorial was written by Karen Pineda and you can find more of their work on their [GitHub profile](https://github.com/k-pineda).
