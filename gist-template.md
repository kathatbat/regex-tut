# Regex Tutorial

Welcome to my regex tutorial on URL validation! In this guide, I'll break down the components of a regular expression used to validate URLs. Whether you're parsing text or building a web application, understanding how to validate URLs effectively is essential.

## Summary

We'll focus on a regex pattern specifically designed to validate URLs:
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

This pattern allows for both HTTP and HTTPS protocols, domain names with various extensions, and optional paths. Throughout this tutorial, we'll dissect each part of this regex to understand how it works.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
Anchors are represented by '^' and '$' and signify the start and end of the string. They ensure that the entire string matches the regex pattern.

An example:
/^https?:\/\/example.com$/
This regex will match URLs that start with 'http://' or 'https://' and end with 'example.com'.

### Quantifiers
Quantifiers control how many instances there are of a specific character or group. In our URL regex, '?', '*', and '{2,6}'are quantifiers used to define optional parts and repetition.

Example: 
/^https?:\/\/[\da-z\.-]+\.com$/
This regex will match URLs that start with 'http://' or 'https://', followed by any combination of alphanumeric characters, dots, or hyphens, and end with '.com'.

### Character Classes
Character classes, shown by square brackets '[]', specify sets of characters that can match at a particular position in the string. In our regex, '[\da-z\.-]' matches alphanumeric characters, dots, and hyphens.

An example:
/^https?:\/\/[\da-z\.-]+\.com$/

### Grouping and Capturing
Grouping, indicated by parentheses '()', allows for creating subpatterns within the regex. This enables us to separate specific components of the URL, such as the protocol, domain, and path.

An example:
/^((https?):\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
The protocol ('http' or 'https') is captured in the first group, the domain name is captured in the third group, and the path is captured in the fifth group. This allows us to extract these components separately for further processing.

### Greedy and Lazy Match
Quantifiers are greedy by default, matching as much text as possible. Adding '?' after a quantifier makes it lazy, matching as little text as possible.

An example:
/^https?:\/\/[\da-z\.-]+?\.com$/
In this regex, the '?' after '+' makes the pattern match the domain part ('[\da-z\.-]+') as few characters as possible.

### Boundaries
Boundary metacharacters, such as '\b' and '\B', specify positions where matches can occur within the text.

An example:
/\bhttps?:\/\/\w+\.com\b/
This regex ensures that the URL starts and ends at word boundaries.

### Look-ahead and Look-behind
Look-ahead and look-behind assertions match a pattern only if it is followed or preceded by another pattern.

An example:
/^https?:\/\/(?=www)\w+\.com$/
In this regex, the '(?=www)' is a positive look-ahead that ensures the domain starts with "www."

## Author

This tutorial is created by Katoria McMullen, a student at EdX and a web developer.
- [GitHub]
  * [kathatbat](https://github.com/kathatbat)
