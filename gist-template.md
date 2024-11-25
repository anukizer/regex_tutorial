# Title (replace with your title)

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Summary
This regex ensures that user input is a valid email address. It validates emails by checking for a specific format: a username, an @ symbol, a domain name, and a valid top-level domain (e.g., .com, .org). We will explore its structure in detail, including anchors, quantifiers, grouping, and character classes.

## Table of Contents

- Anchors
- Quantifiers
- Grouping and Capturing
- Character Classes
- Boundaries
- Author

## Regex Components
### Anchors
Anchors define the start and end points of the regex pattern.

^ ensures that the pattern starts matching from the beginning of the string.
$ ensures that the pattern matches up to the end of the string.
Together, ^ and $ confirm that the entire string is validated as an email address, with no extra characters.

Example: /^example@domain.com$/ // Matches "example@domain.com" but not " example@domain.com ".

### Quantifiers
Quantifiers specify how many times a character or group can repeat.

+: Matches one or more occurrences of the preceding character or group.
In the username section ([a-z0-9_\.-]+), the + ensures that there is at least one valid character before the @.

Example: /[a-z]+/ // Matches "abc", "hello" (one or more lowercase letters).


### OR Operator
Grouping and Capturing
Parentheses () group parts of the regex and capture matched substrings.

([a-z0-9_\.-]+): Captures the username (letters, numbers, underscores, dots, or hyphens).
([\da-z\.-]+): Captures the domain name (letters, numbers, dots, or hyphens).
([a-z\.]{2,6}): Captures the top-level domain (e.g., .com or .org).
Captured groups can be extracted later in programming languages for further use.
Example:
const regex = /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/;
const email = "test@example.com";
const matches = email.match(regex); 
console.log(matches[1]); // Outputs: "test"
console.log(matches[2]); // Outputs: "example"
console.log(matches[3]); // Outputs: "com"


### Character Classes
Character Classes
Character classes define sets of characters to match.

[a-z0-9_\.-]: Matches lowercase letters (a-z), numbers (0-9), underscores (_), dots (.), and hyphens (-).
[\da-z\.-]: Matches digits (\d), lowercase letters, dots, and hyphens.
[a-z\.]: Matches lowercase letters and dots.

### Boundaries
This regex uses boundaries to ensure correct email formatting:

@: Matches the required @ symbol separating the username and domain.
.: Matches the required dot in the domain.
Example: /test@domain.com/ // Validates the placement of "@" and ".".


## Author

This tutorial was created by Anuujin Kizer. I am a web development student passionate about teaching and simplifying complex concepts like regex.







