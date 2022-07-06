# Regular Expressions - Matching A HEX Values

In this file tutorial it is intended to explain how Regex aka regular expressions work. This topic will cover the expression used to match a HEX value and how to validate a HEX value.

## Summary

This tutorial will evaluate the following expressions and how to match the values:

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

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
The forward slash character is used to denote the boundaries of the regular expression: ? The backslash character ( \ ) is the escaping character. It can be used to denote an escaped character, a string, literal, or one of the set of supported special characters.

/this_is_my_regular_expression/  this is a common example of the slashes.

### Anchors
Anchors are regex tokens that don't match any characters but that say or assert something about the string or the matching process. Instead, they match a position before, after, or between characters. They can be used to “anchor” the regex match at a certain position. The caret ^ matches the position before the first character in the string. Applying ^a to abc matches a. ^b does not match abc at all, because the b cannot be matched right after the start of the string, matched by ^. See below for the inside view of the regex engine.
Similarly, $ matches right after the last character in the string. c$ matches c in abc, while a$ does not match at all.

### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. 
In our example above, {6} indicates that there are 6 instances of the string in the preceding bracket expression. That implies that this quantifier will allow exactly 6 characters in the string containing characters between a-f and/or integer between 0-9. {3} indicates that there are 3 instances of the string in the preceding bracket expression. That implies that this quantifier will allow exactly 3 characters in the string containing characters between a-f and/or integer between 0-9.

### Grouping Constructs
Grouping constructs delineate the subexpressions of a regular expression and capture the substrings of an input string. Grouping can be used in many ways:
1. To match a subexpression that is repeated in the input string.
2. Apply a quantifier to a subexpression that has multiple regular expression language elements. 
3. Include a subexpression in the string that is returned by the Regex.Replace and Match.Result methods.
4. Retrieve individual subexpressions from the Match.Groups property and process them separately from the matched text as a whole.
([a-f0-9]{6}|[a-f0-9]{3})
In the example above the grouped expression is a bracket expression whose details are provided in the section below. Ultimately the end string anchor $ is applied to this grouping.

### Bracket Expressions
By placing part of a regular expression inside round brackets or parentheses, you can group that part of the regular expression together. This allows you to apply a quantifier to the entire group or to restrict alternation to part of the regex. Only parentheses can be used for grouping. Since hex values can contain lowercase letters that range from a to f or numbers that range from 0 to 9, we would place exactly what we want to match within those brackets. We can denote that we are searching for the full range of those characters with a - symbol in between to specify that these are a range of characters.
From our example above this would be what a bracket expression would look like. 
[a-f0-9]

### Character Classes
In the context of regular expressions, a character class is a set of characters enclosed within square brackets. It specifies the characters that will successfully match a single character from a given input string.

### The OR Operator
The OR operator is the symbol |. We can put that between two bracket expressions in order to specify that we are looking for one bracket expression or the other. What we are putting within our subexpression will look like the following:
/[a-f0-9]{3}|[a-f0-9]{6}/

### Flags
Regular expressions may have flags that affect the search. You can search for items that are on muiltiple lines, case sensitive, specific matches, and positions.

### Character Escapes
The backslash in a regular expression precedes a literal character. You also escape certain letters that represent common character classes, such as \w for a word character or \s for a space. 

## Author

My Name is Lea Guerrero. I am currently a senior graphic designer in the gaming industry and I am an aspiring web developer. I have a passion for UI but excited to learn how to entagrate UX to be a more well rounded developer.

Github: https://github.com/lealinnea?tab=repositories
