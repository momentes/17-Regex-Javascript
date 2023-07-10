# Module-17-Challenge
Bootcamp Module 17 Challenge - Regex Tutorial

Regular expressions, also known as regex, are patterns composed of characters that are used for searching and manipulating text. They are commonly utilized in word processors, text editors, and search engines. One specific example of a regex pattern is designed to identify hexadecimal values. Hexadecimal values follow a letter-and-whole-number format and are often challenging to locate due to their tendency to start with a "#" symbol and have varying lengths.

## Regular Expression to Maching Email Expression

Example of Regex used to match Email addresses:

    /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/


Programmers utilize regular expressions (Regex) to validate the format of email entries. Regex is highly effective in verifying the legitimacy of an email address, as it ensures that the entered email adheres to the required format. This validation process significantly reduces errors in email recipient and delivery. In general, Regex applies a set of rules for a valid email format, and any email that deviates from this pattern is considered invalid. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)
- [Flags](#flags)

### Anchors

Within this regular expression, there are two distinct anchors: ^ and $.

The ^ anchor is employed to identify and match the commencement of a line or string, while the $ anchor is utilized to locate and match the conclusion of a line or string, taking into consideration the characters that precede it. In the context of this particular regular expression, these anchors are strategically employed to ensure that the entire string aligns with the specified pattern.

In the context of the "Matching an Email" regex, it is imperative that the string commences and concludes with a segment that satisfies the specified pattern `([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})`. The regular expression does not incorporate the quantifier {2,6} preceding the $ character. The omission of this component is intentional, as it pertains to a specialized element known as a quantifier. 

If the input string fails to commence with the specified pattern indicated by the regular expression or does not conclude with the pattern, the regular expression will not yield a match. In order for a successful match to occur, it is essential for the input string to strictly adhere to the prescribed pattern from its beginning to its end

### Quantifiers

Quantifiers play a crucial role in regular expressions as they determine the number of times a specific character or group of characters should be matched. 

In the regular expression `([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})`, the following quantifiers are used:

* `+` (plus): It appears after ([a-z0-9_.-]) and ([\da-z.-]), indicating that the preceding character sets should match one or more times.

* `{2,6}`: It appears after ([a-z.]), specifying that the preceding character set should match at least 2 times and up to 6 times.

These quantifiers define the repetition behavior of the respective character sets in the regular expression.

### Grouping Constructs

Grouping constructs in regular expressions, represented by parentheses (), serve multiple purposes. They allow for capturing groups, enabling extraction or referencing of matched content. They facilitate logical groupings and alternation using the | character. Quantifiers can be applied to groups to specify the number of repetitions. Additionally, grouping constructs can modify the behavior of the contained subpattern, such as creating non-capturing groups. Overall, these constructs provide flexibility and control, allowing for the grouping of characters or subpatterns as a single unit in regular expressions.


In the regular expression ([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6}), the following grouping constructs are used:

([a-z0-9_.-]+): This is a capturing group that matches and captures one or more lowercase letters, digits, underscores, dots, or hyphens.

([\da-z.-]+): This is another capturing group that matches and captures one or more digits, lowercase letters, dots, or hyphens.

([a-z.]{2,6}): This is a capturing group that matches and captures lowercase letters or dots, with a minimum of 2 and a maximum of 6 repetitions.

These grouping constructs allow for capturing specific portions of the matched string, such as the username, domain name, and top-level domain, for further processing or extraction.


### Bracket Expressions