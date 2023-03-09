# REGEX TUTORIAL w/ Find Email Example

Regular Express, or Regex, is a sequence of characters defining a search pattern. By understanding Regex’s syntax, you can perform more dynamic searches on text. With traditional literal searches, a user typically looks for a specific character or string meanwhile with Regex, a user can search for different variations in characters and strings.

## Summary

In this tutorial we will examine the Regex used for matching emails: 

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/


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

## Regex Components

### Anchors

There are two types of anchors: ^ AND $
-	^ signifies that the string should begin with the following set of characters. In our example, the email should begin with ^([a-z0-9_\.-]+)
-	$ signifies what the string should end with. In our example, the email should end with ([a-z\.]{2,6})

### Quantifiers

Quantifiers help us set limits on the strings we want to match. Here are some examples:
-	*—Matches the pattern zero or more times
-	+—Matches the pattern one or more times
-	?—Matches the pattern zero or one time
-	{}—Curly brackets can provide three different ways to set limits for a match:
    o	{ n }—Matches the pattern exactly n number of times
    o	{ n, }—Matches the pattern at least n number of times
    o	{ n, x }—Matches the pattern from a minimum of n number of times to a maximum of x number of times
In our example, we can see the quantifier {2,6} meaning the final part of the string should have a minimum length of 2 and maximum of 6.


### OR Operator

The | means OR, meaning the Regex will check between both values. For example, A|B will check if the character is either A or B. 

The [] brackets can be used to check if any of the values within match. Example of this in the email regex would be [a-z\.]; the expression is checking if any of the letters are lowercase letters or if a . is present.


### Character Classes

The following syntaxes are used to define a range of characters. For example:
-	. means any character
-	\d means any number (0-9)
-	\w means any alphanumeric character including _ (A-Z,a-z,0-9_)
-	\s means a single white space including tabs and line breaks


### Flags

A regex is wrapped with /, a flag is typically placed outside the second /
Flags define additional functionality or limits to the regex. Here are some examples:

- g—Global search: the regex should be tested against all possible matches in a string.
- i—Case-insensitive search: case should be ignored while attempting a match in a string
- m—Multi-line search: a multi-line input string should be treated as multiple lines


### Grouping and Capturing

Regex can be grouped into subexpressions which are defined with (). Within our email example, a group is ([a-z0-9_\.-]+) which searches and captures any string with a-z, 0-9, or _.-

Groups can be named with (?<name>...) to be referenced later.

### Bracket Expressions

A bracket expression means to search for anything contained between the brackets []. Like mentioned previously with our example, [a-z0-9_\.-] will search for any a-z, 0-9, or _.-

### Greedy and Lazy Match

Greedy Search represents ( * + {} that have been mentioned previously. The search will try to match the longest string possible.

Lazy Search: This search will try to match the fewest characters possible. The lazy search is denoted by adding a “?” after the quantifier. 

### Boundaries

\b can be used to only search for what is in between the boundaries. An example is \bday\b will match with “day” but not “Friday”

### Back-references

Backreferences allow you to refer to a previously matched group within the same regular expression. They are denoted by \1 where the “1” can be any group number. For example, the regular expression (\w+)\1 matches a word and then the exact same word that was matched earlier (backreferenced by \1). You could also back reference by name using (\k<name>)

### Look-ahead and Look-behind

Look-ahead will only match if the next part of the string following a string matches as well. For example, b(?=g) will render a match on the string “bg” and return b, but it will not match for “b”, “bx”, or “gb”

Look-behind is the same concept but instead of looking forward, you are looking backward. For example, (?<=x)a will render a match on the string “xa” and return a, but it will not match for “a”, “qa” or “xa”


## Author

https://github.com/Mdwag316