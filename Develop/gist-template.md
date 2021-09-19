## Regex HM

As a Full Stack Web Dev student, I developed a tutorial explaining a specifics of regex so that we can understand the search pattern the regex defines

## Summary

This is a tutorial breakdown on how Regex is used to match a Hex Value in a body of text. /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ is the syntax that I will be using.

Hex Code is a way to identify color. It is always in a 6-digit alphanumeric sequence.

The regex string I am using will return a # Number sign character followed by either a 6 or 3 character length code with only lowercase letters a,b,c,d,e,or f or numbers 0,1,2,3,4,5,6,7,8, or 9.

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

The starting ^ caret and ending $ dollar sign are both anchors in the example string. /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

The ^caret matches at the start of the string the regex pattern is applied to.
The # Number Sign following the starting ^caret is a literal character and a #Number Sign MUST be at the start of the string.
The $ dollar sign matches at the end of the string the regex pattern is applied to. This signifies the end of the string.

### Quantifiers

Each quanifier denotes how many times the previous token will be matched. There are 3 quanitfiers in the example syntax. /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

1. The first $ Dollar Sign ( which I will also go over in the Greedy section) This signifies that the # Number Sign will match 0-1 times.

2. {6} This signifies that the previous token [a-f0-9] will have 6 characters match within that set.

3. {3} This signifies that the previous token [a-f0-9] will have 3 characters match within that set.


### OR Operator

The example syntax uses an OR operator known as | Vertical line or pipe. There is a | Pipe between two characters classes. This creates 2 alternative groups. This allows the search to find and match either group.

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

- The first alternative is before the | pipe [a-f0-9] will return 6 characters.

- The second alternative after the | Pipe will return 3 characters.

### Character Classes

Character classes are found betwen [...] square brackets. They are used to create a list of allowable characters. In the example syntax there are two character classes. They look exactly the same because they are, however the quantifier is what makes each class return a different number of characters.

The example uses [a-f0-9]

- a-f = This is the range that matches a case sensitive single character of: a,b,c,d,e, or f.
- 0-9 = This is the range that matches a case sensitive single digit of: 0,1,2,3,4,5,6,7,8, or 9


### Flags

Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression.

- i Ignores case
- g Global search retain the index of the last match, allowing subsequent searches to start from the end of the previous match. Without the global flag, subsequent searches will return the same match.
- m Multiline flag When the multiline flag is enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.
- u Unicode
- y The expression will only match from its lastIndex position and ignores the global (g) flag if set. Because each search in RegExr is discrete, this flag has no further impact on the displayed results.
- s Dot (.) will match any character, including newline.
NOTE: Unicode is an information technology standard for the consistent encoding, representation, and handling of text expressed in most of the world's writing systems


### Grouping and Capturing

Anything found inside of ( round brackets ) creates a capture group. Everything inside that (...) is treated as a single unit. So with the example syntax /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ there is one capture group with two characters sets seperated by an OR Operator.



### Bracket Expressions

A bracket expression enclosed in square brackets is a regular expression that matches a single character, or collating element. If the initial character is a circumflex ^, then this bracket expression is complemented.

See Character Class to see some examples.

### Greedy and Lazy Match

- 'Greedy' means matching the longest possible string. A Greedy quantifier tells the engine to match as many instances of its quantified token or subpattern as possible. This behavior is called greedy.

- 'Lazy' means matching the shortest possible string. A lazy quantifier tells the engine to match as few of the quantified tokens as needed. As you'll see in the table below, a regular quantifier is made lazy by appending a ? question mark to it.

### Boundaries

The \b is an anchor like the caret and the dollar sign. It matches at a position that is called a “word boundary”. This match is zero-length.

Characters that are matched by the short-hand character class \w are the characters that are treated as word characters by word boundaries.

Since digits are considered to be word characters, \b4\b can be used to match a 4 that is not part of a larger number. So saying \b matches before and after an alphanumeric sequence is more exact than saying “before and after a word”.

\B is the negated version of \b. \B matches at every position where \b does not. Effectively, \B matches at any position between two word characters as well as at any position between two non-word characters.

There are more boundries with the Regex Engine. Some examples include Tcl, GNU, and POSIX.

### Back-references

Backreferences match the same text as previously matched by a capturing group. Suppose you want to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag.

For Example: <([A-Z][0-9]*)\b[^>]*>.*?</\1> This regex contains only one pair of parentheses, which capture the string matched by [A-Z][0-9]*. This is the opening HTML tag. The backreference \1 references the first capturing group. \1 matches the exact same text that was matched by the first capturing group. The / before it is a literal character. It is simply the forward slash in the closing HTML tag that we are trying to match.

### Look-ahead and Look-behind

- (?=ABC) is a postive lookahead and it matches a group after the main expression without including it in the result.

- (?!ABC) is a negitive lookahead and it specifies a group that can not match after the main expression (if it matches, the result is discarded)

- (?<=ABC>) is a postive lookbehind and matches a group before the main expression without including it in the result.

- (?<!ABC) is a negitive lookbehind and Specifies a group that can not match before the main expression (if it matches, the result is discarded).

- Lookaheads and lookbehinds forces the main expressions to be what you have defined it as. Without it being exactly what it is it will not be accepted as a valid input.


## Author

A Student of the University of Carleton Coding Bootcamp Yussef Rafat 
- GitHub : https://github.com/yussefrafat

