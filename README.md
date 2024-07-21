# Matching a URL with Regular Expressions

Regular expressions are powerful tools for pattern matching in text. This guide explores a regex pattern designed to match URLs, explaining each component and its role in capturing different parts of a URL.

## Summary

This regex pattern aims to match URLs that may start with "http://" or "https://", followed by a domain name (with or without "www"), and optional path segments. It includes handling for common URL structures while being adaptable for various URL formats.

```regex
^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

The regex uses `^` to match the start and `$` to match the end of the string, ensuring it captures the entire URL.

### Quantifiers

Quantifiers like `?` (zero or one occurrence) and `*` (zero or more occurrences) are used to specify optional parts of the URL, such as the protocol (`http://` or `https://`) and path segments.

### OR Operator

The regex employs `?` inside `(https?:\/\/)?` to match an optional "s" in "https" while allowing "http://" as well.

### Character Classes

Character classes such as `[\da-z\.-]` match specific sets of characters:
- `\d`: Matches digits (0-9).
- `a-z`: Matches lowercase letters.
- `\.-`: Matches literal dots (`.`) and dashes (`-`).

### Grouping and Capturing

Parentheses `(...)` are used for grouping parts of the regex together, allowing quantifiers (`*`, `?`) to apply to entire groups like `([\/\w \.-]*)`.

### Bracket Expressions

Bracket expressions `[...]` define sets of characters to match. For instance, `[a-z\.]` matches lowercase letters and dots.

### Greedy and Lazy Match

The `*` quantifier is greedy by default, matching as many characters as possible. `*?` could be used for a lazy match where necessary.

### Boundaries

The anchors `^` and `$` ensure the regex matches from the start to the end of the string, effectively marking the boundaries of the URL.

### Back-references

Back-references (`\1`, `\2`, etc.) are not explicitly used in this regex but could be employed in more complex patterns to refer to previously captured groups.

### Look-ahead and Look-behind

N/A

## Author

This guide was created by CQC0013. Find more about me on [GitHub](https://github.com/cqc0013).