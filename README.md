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

In the regular expression `([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})`, the regex anchors ^ and $ are not explicitly used. However, it's important to note that anchors can play a significant role in email-related regular expressions.

The `^` (caret) anchor is typically used to match the start of a line or string. In the context of email validation, it can be employed at the beginning of a regular expression to ensure that the email pattern starts at the very beginning of the input string.

The `$` (dollar sign) anchor, on the other hand, is used to match the end of a line or string. In relation to email validation, it can be used at the end of a regular expression to ensure that the email pattern extends until the very end of the input string.

While the given regular expression does not explicitly utilize these anchors, their inclusion is often recommended in a more comprehensive email validation regex pattern to ensure that the entire input string is considered for matching against the email pattern.

### Quantifiers

Quantifiers play a crucial role in regular expressions as they determine the number of times a specific character or group of characters should be matched. 

In the regular expression `([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})`, the following quantifiers are used:

* `+` (plus): This quantifier is used in ([a-z0-9_.-]+) to match the preceding character set [a-z0-9_.-] one or more times. It ensures that there is at least one alphanumeric character, underscore, dot, or hyphen before the @ symbol.

* `*` (asterisk): This quantifier is used in ([\da-z.-]+) to match the preceding character set [\da-z.-] zero or more times. It allows for any combination of digits, lowercase letters, dots, or hyphens after the @ symbol.

* `{2,6}`: This quantifier is used in ([a-z.]{2,6}) to specify a range for the preceding character set [a-z.]. It allows for the character set to repeat between 2 and 6 times. In this case, it ensures that the top-level domain (TLD) part of the email address consists of 2 to 6 lowercase letters or dots.

These quantifiers help define the matching criteria for different parts of the email address pattern in the regular expression.

### Grouping Constructs

Grouping constructs in regular expressions, represented by parentheses (), serve multiple purposes. They allow for capturing groups, enabling extraction or referencing of matched content. They facilitate logical groupings and alternation using the | character. Quantifiers can be applied to groups to specify the number of repetitions. Additionally, grouping constructs can modify the behavior of the contained subpattern, such as creating non-capturing groups. Overall, these constructs provide flexibility and control, allowing for the grouping of characters or subpatterns as a single unit in regular expressions.

In the regular expression `([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})`, the following grouping constructs are used:

* `([a-z0-9_.-]+)`: This is a capturing group that matches and captures one or more lowercase letters, digits, underscores, dots, or hyphens.

* `([\da-z.-]+)`: This is another capturing group that matches and captures one or more digits, lowercase letters, dots, or hyphens.

* `([a-z.]{2,6})`: This is a capturing group that matches and captures lowercase letters or dots, with a minimum of 2 and a maximum of 6 repetitions.

These grouping constructs allow for capturing specific portions of the matched string, such as the username, domain name, and top-level domain, for further processing or extraction.


### Bracket Expressions

A bracket expression, denoted by square brackets [ ] in regular expressions, defines a character class or set of characters that can be matched at a specific position. It allows for specifying individual characters or ranges within the brackets to define the valid options. This provides flexibility in defining the acceptable characters within the regex pattern.

In the regular expression ([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6}), the following bracket expressions are used:

* `[a-z0-9_.-]`: This bracket expression specifies a character class that includes lowercase letters (a-z), digits (0-9), underscores (_), dots (.), and hyphens (-). It matches any single character from this set.

* `[\da-z.-]`: This bracket expression represents a character class that includes digits (\d), lowercase letters (a-z), dots (.), and hyphens (-). Again, it matches any single character from this set.

* `[a-z.]`: This bracket expression defines a character class containing lowercase letters (a-z) and dots (.). It matches any single character from this set.

These bracket expressions allow for matching specific characters or ranges within the email pattern, such as valid alphanumeric characters, dots, underscores, and hyphens.

### Character Classes

Character classes in regular expressions are a way to define a set or range of characters that can be matched at a specific position, allowing for flexible and concise pattern matching.

In the regular expression `([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})`, character classes are used to define specific sets or ranges of characters that can be matched for different parts of the email pattern.

* `[a-z0-9_.-]`: This character class matches any lowercase letter (a-z), digit (0-9), underscore (_), dot (.), or hyphen (-). It is used in ([a-z0-9_.-]+) to match one or more occurrences of these characters before the @ symbol.

* `[\da-z.-]`: This character class matches any digit (0-9), lowercase letter (a-z), dot (.), or hyphen (-). It is used in ([\da-z.-]+) to match one or more occurrences of these characters after the @ symbol.

* `[a-z.]`: This character class matches any lowercase letter (a-z) or dot (.) and is used in ([a-z.]{2,6}) to match the top-level domain (TLD) part of the email address, which should consist of 2 to 6 lowercase letters or dots.

By using character classes, the regular expression defines the allowed characters for different portions of the email pattern, providing a flexible and precise matching mechanism.

### Character Escapes

Character escape in regular expressions is a mechanism that allows special characters to be interpreted literally rather than having their special meaning, ensuring that they are matched as normal characters within the pattern.

In the regular expression `([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})`, character escapes are not explicitly used. However, character escapes in regular expressions typically involve the backslash \ followed by a special character to be escaped.

In the context of email validation, character escapes might be used to match special characters like the dot (.), hyphen (-), or other characters that have special meanings within regular expressions. For example, if we wanted to match a literal dot, we could use the escape sequence \. to ensure it is treated as a regular character rather than a special metacharacter.

In the given regular expression, since the characters [a-z0-9_.-], [\da-z.-], and [a-z.] do not include any special characters that require escaping, character escapes are not necessary.

### Flags

Flags in regular expressions are additional parameters that modify the behavior of pattern matching. They provide extra control and options for regex matching operations. Flags are typically represented as single characters, such as "i", "g", "m", and so on. Each flag serves a specific purpose, such as case-insensitive matching, global matching, multiline matching, and more. By using flags, regex patterns can be customized to meet specific requirements, enabling more versatile and powerful text matching capabilities.

In the regular expression `([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})`, there are no explicit regex flags used. However, flags can be added to modify the behavior of the regular expression.

Some commonly used flags in regular expressions include:

* `"i"` flag: Enables case-insensitive matching. For example, /pattern/i would match both uppercase and lowercase characters.

* `"g"` flag: Enables global matching, searching for multiple occurrences of the pattern within the input string.

* `"m"` flag: Enables multiline matching, allowing the pattern to match across multiple lines.

In the given regular expression, if we were to add the "i" flag (/pattern/i), it would allow case-insensitive matching for the email pattern. This means that both uppercase and lowercase letters would be considered valid within the email address. However, without any explicit flags in the provided regular expression, the pattern matching will default to its default behavior based on the regex engine being used.

## Author

Bryan Seng
**Github** : https://github.com/momentes/17-Regex-Tutorial

Thank you
End.        
<img src="/images/business-cat1.jpg" width=15%>

