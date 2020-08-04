# Regular Expression

## What Is ?

- What is Regex ? Sequence of characters that define a search pattern.
- What for is Regex ? **Find or / and Replace Operation on String**, or for **Input Validation**.
- Setiap karakter dari sebuah regex itu bisa **metacharacter**, atau **literal character**.
- Ada sesuatu yang namanya Regex Processor, itu bisa dibilang enginenya, dan approachnya katanya kurang lebih gini : "One possible approach is the Thompson's construction algorithm to construct a nondeterministic finite automaton (NFA), which is then made deterministic and the resulting deterministic finite automaton (DFA) is run on the target text string to recognize substrings that match the regular expression"
- In the POSIX standard, Basic Regular Syntax (BRE) requires that the metacharacters ( ) and { } be designated \(\) and \{\}, whereas Extended Regular Syntax (ERE) does not.

## How to Use ?

### Token / Metacharacter List

| Token        | Description                                                  | Example                                                      |
| ------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
|              | **Basic Tokens**                                             |                                                              |
|              | literal                                                      | `abc` ⇒ abc                                                  |
| .            | wildcard                                                     | `...` ⇒ abc, def                                             |
| \|           | or                                                           | `gray\|grey` ⇒ gray, grey                                     |
| ( ... )      | grouping / subexpression                                     | `gr(a\|e)y` ⇒ gray, grey                                     |
|              | **Quantifiers**                                              |                                                              |
| ?            | zero or one                                                  | `colou?r` ⇒ color, colour                                    |
| *            | zero or more                                                 | `ab*c` ⇒ ac, abc, abbc, abbbc                                |
| +            | one or more                                                  | `ab+c` ⇒ abc, abbc, abbbc                                    |
| { n }        | matched n times                                              | `ab{3}c` ⇒ abbbc                                             |
| { min, }     | matched min or more times                                    | `ab{3,}c` ⇒ abbbc, abbbbc                                    |
| { min, max } | matched at least min times, but not more than max times      | `ab{3,5}c` ⇒ abbbc, abbbbc, abbbbbc                          |
|              | **More Tokens**                                              |                                                              |
| [ ... ]      | matched a single character that is contained within the brackets | `[abc]` ⇒ a, b, c <br />`[a-z]` ⇒ a, b, sampai z (istilahnya range) <br />`[a-cx-z]` ⇒ a, b, x, y, z<br />`[.]` ⇒ . |
| [^ ... ]     | matched a single character that is not contained within the brackets | `[^abc]` ⇒ d, e, f, dst <br />`[^a-y]` ⇒ z, dst              |
| \w           | matches alphanumeric character                               | `\w` ⇒ a, b, 1, 2, dst                                       |
| \W           | matches non-alphanumeric character                           | `\W` ⇒ !, @, #, dst                                          |
| \s           | matches whitespace                                           | `\s` ⇒ ' '                                                   |
| \S           | matches anything but whitespace                              | `\S` ⇒ a, b, dst                                             |
| \d           | matches a digit                                              | `\d` ⇒ 1, 2, dst                                             |
| \D           | matches a non-digit                                          | `\D` ⇒ a, b, dst                                             |
| \b           | matches zero space between \w and \W                         | `\b` ⇒ a% (position 1)                                       |
| ^            | matches starting position of the string (or line)            | `^hello` ⇒ hello (line1), hello (line2)                      |
| $            | matches ending position of the string (or line)              | `z$` ⇒ abcz                                                  |
| \A           | matches begining of string (but not a line)                  | `\A` ⇒ h for <br /><br />hello <br />world                   |
| \Z           | matches end of string (but not a line)                       | `\Z` ⇒ d for <br /><br />hello <br />world                   |
| \n           | Backreferences. Matches the n-th marked subexpression matched (n is digit from 1 to 9) | `(.)(..)\1` ⇒ abba <br />`(.)(..)\2` ⇒ abbbb                 |



