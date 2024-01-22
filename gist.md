# Regex Breakdown - Common Email Pattern

Often when dealing with large blocks of text or code, a need to identify a pattern arises to manipulate or check the data. This type of pattern-matching orginated from the mathmatical concept of regular-sets and has been incorporated into many computer programming languages to be leveraged. There are many common patterns developers use in their code, but this article will focus on the Email Pattern as this is a very common data-type that almost everyone is familiar with.

## Summary

The Email Pattern sets out to check the validity of a string that it correctly corrects an email address. As we all know, email addresses must contain an @ symbol along with some other descriptive text. An example of an email regex pattern can look like this:

```javascript
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/;
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

A requirement of Regular Expressions in Javascript is the slash characters (/) at the beginning and end of the string literal.

### Anchors

There are two anchors present in the email regex pattern. First being the ^ character at the second index. It signifies that this is the start of the string and whatever next character follows is the first character. The second Anchor, the $ sign, signifies the end of the string and the last character has to match the regex pattern

### Quantifiers

Quantifiers give regular expressions the ability to measure the lengths of the inputs. This allows the user to set limits on the amount of characters, or the amount of times a pattern matches in the given string literal. There a couple quantifiers present in the email pattern. First being the + sign. The + means that preceding pattern needs to match 1 or more times. We do this twice (essentially checking that there is at one character on each side of the @ symbol). The last quantifier is the bracket notation {} on the end off the string. This is restricting the third subexpression to being between 2-6 characters.

### Grouping Constructs

To allow for more complex pattern matching, regular expressions givens you a convient way to group your expressions together with parentheses (). This allows you to chain expressions together into subexpressions to be evaluated seperately. We have 3 group constructs in the email pattern. First before the @. Second after the @. Third after the .

### Bracket Expressions

The bracket expression [] is where the possible characters for your pattern will be defined. In our example, a-z means any lower case letter bettwen a to z. 0-9 means any digit. The inclusion of the underscore in the bracket notation means that underscores are a valid character to be included. The \. means that the period can also be used. Finally the inclusion of the dash - means that the dash is also a valid character. The second bracket expression is similar, but starts off with 'd' meaning any digit. The da-z means any digit or any lower case letter. dots and dashes are also valid. The third subexpression allows only a-z characters plus a dot.

### Character Classes

Character classes are predefined groups of characters that can be easily added to the expression. An example of this is the \d we saw in the bracket expression. \d is a character class for digits so [\d] means the same thing as [0-9]

### The OR Operator

The OR operator gives regular expressions the ability to still validate without matching on the specific order. It gives you the ability to match on multiple things that could possibly be out of order. Since email's are a highly structured string, there is not an OR operator in the email pattern

### Flags

Flags are an extra feature of Regular Expressions that allow the user to define some component of the pattern AFTER the expression is already defined. This means flags are placed after the second slash. A good example of this could the inclusion of the i flag, the case-insensitive flag, if we wanted to ignore the case of the characters in our string without having to add a-zA-Z into the brack expression.

### Character Escapes

As certain characters are used as part of the syntax of regular expressions, but often you will want to actually pattern match on those very same characters. Character escapes provide a simple way to include those characters. A backslash \ plus the character such as \. in our example adds the period to the pattern match.

## Author

Mark Forte is a software engineer from Philadelphia, Pennsylvania.

Github Link: https://github.com/mforte215
