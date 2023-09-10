# Matching a Hex Value

Introductory paragraph (replace this with your text)

## Summary

Regular expressions are a series of special characters that define a search pattern. The following regular expression, which we’ll call “Matching a Hex Value", is a search pattern that identifies valid hex codes.

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

Essentially, the above string of text gives our search function three parameters:

The string must begin with one pound sign (#)

The part of the string after the pound sign must be 6 or 3 characters long

The part of the string after the pound sign must only contain letters a through f and numbers 0 through 9



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
A regular expression is a literal, which can't be parsed into an operation by the regex engine. In order for our search function to work, we need to add slashes around our expression to turn the literal characters into metacharacters. If we check out our hex code regex, we can see those slash characters around the expression:

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/ 

Let's go ahead and break this expression down some more.

### Anchors
We have two types of anchors in our expression, namely ^ and $ .
The first anchor we see is the caret (^), which signifies a string that begins with the characters after the anchor. This can be either an exact string, like ^Cat (which would have matches "Cat" or "Catastrophe" or "Cat cafe", but not "cat" - regexes are case-sensitive!), or it can be a range of matches denoted by bracket expressions.
The other anchor, the dollar ($), specifies that the target string must have the preceding characters at the end. For example, code$ would match "Hex code" or "decode" but not "code red" or "i <3 code!!!".

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/ 

Therefore, in our above "Matching a Hex Value" regex, the string must begin with a pound sign (#) and must end with the string defined by the expression inside the parentheses, [a-f0-9]{6}|[a-f0-9]{3}, which we'll continue breaking down in the following sections.

### Grouping and Capturing
The parentheses around the [a-f0-9]{6}|[a-f0-9]{3} subexpression serve a vital purpose in regex processing, in this case by grouping the subexpression with the $ anchor. This way, our computer knows to use the entire subexpression as valid parameters to feed into the "what goes at the end?" question postulated by the anchor.

### OR Operator
This string, [a-f0-9]{6}|[a-f0-9]{3}, is separated into two parts using the OR operator (|). This way, either [a-f0-9]{6} or [a-f0-9]{3} can be true for our ending string. ELABORATE

### Bracket Expressions
The range of characters our search target needs to include are specified within [square brackets] before our quantifiers. On both sides of the OR operator, we have [a-f0-9] as our bracket expression. ELABORATE

### Quantifiers
The quantifiers of our string are specified within {curly brackets} after our bracket expressions. WHAT ARE THEY FOR We have two quantifiers separated by an OR operator, namely {6} and {3}. This means that, for our expression, we're searching for a string that has either 6 or 3 characters after the pound sign. 

Usually, you'll see hex codes with 6 characters, like #dec0de (pastel purple), but when both r, g, and b values match, such as #331144 (deep purple) or #00ddbb (bright teal), the hex code can be shortened to 3 digits. In these examples, we'd get #314 and #0db respectively, and anyone who recognizes it as a hex code will know to double each digit.

### Character Classes

### Flags





### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
