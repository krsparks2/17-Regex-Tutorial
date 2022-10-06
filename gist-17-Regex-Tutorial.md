#  17 Regex Tutorial

Regular expressions, or regex for short, are a series of special characters that define a search pattern. Take the following example of a regular expression, which we’ll call “Matching an Email”:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

In this tutorial I will explain what each portion of the above expression does what. 

The [a-z] portion says the string can contain any lowercase letter between a-z, but this applies to lowercase ONLY as regex is case sensitve.  If we wanted to use uppercase letters we would use [A-Z].  To get both lower and uppercase you can combine the two to be [a-zA-Z].

The [0-9] portion allows the string to contan any number between 0 and 9. The \b matches any Arabic Numeral digit and is equivalent to [0-9]. 

The _\.- allows the string to use hyphens, underscores and periods.

And {2,6} allows the string preceeding it to be between 2 and 6 characters long.

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
 Because regex is considered a literal, the pattern has to be wrapped in /.  As you can see the above "matching an email" expression has the brackets at the begining and the end of the expression.  You can also create the regex expression using a constructor function which uses single quotes ('') to wrap the regex expression.

### Anchors
 The characters ^ and $ are anchors.  The ^ signifies a string that begins with the characters that follow it.  The $ signifies a string that ends with the characters before it.

### Quantifiers
Quantifiers set the limits of the string that the regex matches.  Quantifiers will match as many occurances of the pattern as possible.  Quantifiers are:

* matches the pttern 0 or more times
+ matches the pattern 1 or more times
? matches the pattern 0 or 1 times
{} curly brackets provide 3 different ways to set limits for the match
    { x } matches the pattern x number of times
    { x, } matches the pattern at least x times
    { x, y } matches the pattern a minimum of x times and a maximum of y number of times

### OR Operator
Regex allows an OR operator (|) which is not used in this expression.

### Character Classes
A character class defines a set of characters any of which can be in an input string to match.  Some common character classes include:
. which matches an character except (\n)
\d matches any arabic numeral digit (equivalent to [0-9])
\w matches any alphnumeric character from the latin alphabet this is equivalent to [A-Za-z0-9_]
\s matches a single whitespace character this includes tabs and line breaks

### Flags
Flags are placed at the end of the regex after the second slash and they define additional limits or functionality.  There are 6 flags that can be used, the most common of which are:
g global search
i case sensitive search
m multi-line search

### Grouping and Capturing
More complicated regex expressions allowing you to check multiple parts of the string will need to be broken up using grouping contructs.  You group a section of a regex within a pair of parentheses (()).  The "Matching an Email" regex has 3 of these sections, called a subexpression.  Grouping contructs are either capturing or non-capturing, capturing constructs capture the matched sequences for later re-use and non-capture constructs do not.  If you want to make the construct a non-capturing construct you would put a ?: at the begining of the expression inside the parentheses

### Bracket Expressions
Bracket Expressions a.k.a. Positive Character Groups outline the characters we want to match.  In the "Matching an Email" regex above we have three of these bracket sections:

[a-z0-9_\.-] this bracket expression looks for a string that contains any lowercase letter between a and z, any number between 0 and 9 and allows the special characters of underscore, hyphens and periods.
[\da-z\.-] this bracket expression looks for a string that contains any lowercase letters between a and z and any number between 0 and 9 and allows the special characters of hyphens and periods.
[a-z\.] this bracket expression looks for a string that contains any lowercase letter between a and z

### Greedy and Lazy Match
A greedy match, matches as many instances as possible. A lazy match, matches as few instances as possible.  The "Matching an Email" regex is a greedy match.

### Boundaries
The regex exxpression "Matching an Email" does not use a boundary.  A word boundary is denoted by a (\b) and is used to match a sequence of letters (or digits) on their own, or to ensure that they occur at the begining or end of a string.

### Back-references
Back-references identify a previously matched string and looks for the exact same text again, this is denoted by (\N) and (\k<name>).  The "Matching and Email" regex does not have any back-references.

### Look-ahead and Look-behind
The look-ahead and look-behind syntax allows us to find matches for a pattern that are followed (look-behind) or preceded (look-ahead) by another pattern.  (?!) is a negative look-ahead, (?=) is a positive look-ahead.  (?<=) is a positive look-behind and (?<!) is a negative look-behind.  The "Matching and Email" regex does not have any look-ahead or look-behind syntax in it.

## Author

Keli Sparks
Git Hub - https://github.com/krsparks2