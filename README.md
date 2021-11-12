# Regular Expressions Tutorial - Email Format

## Summary 
This is a tutorial that outlines regular expressions or RegEx for short. Regex is string of special character that defines a search pattern.
The below line of code may look like a bunch of gibberish but it is actually a regex that will validate whether or not the input is an email address.
This tutorial will break down the regex to help you understand what each part means. 

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents
- [Summary](#summary) 
- [Anchors](#anchors)
- [Bracket Expressions](#brackets)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping)
- [The OR Operator](#or)
- [Character Escapes](#escapes)
- [Character Classes](#classes)
- [Flags](#flags)
- [Author](#author)

# Regex Components

## Anchors
Anchors are used to identify the beginning and ending of a regex. The caret^ is used to identify the beginning and the dollar sign$ is used for the end.

<a name="brackets"></a>
## Bracket Expressions
Bracket Expressions [] indicates a range of characters that should match. Unless, there is a ^ at the beginning of the bracket. If this is the case, the characters that follow should NOT match. Looking at our example, we have 3 sets of brackets. 
  - [a-z0-9_\.-]
  - [\da-z\.-] 
  - [a-z\.]
  - 
 Let's break it down as follows. 
  - [a-z] the string can contain any lowercase letter a-z ONLY. Regex are case sensitive. If we want to match letters in uppercase only, we would want to use [A-Z]. If we want to match both lowercase and uppercase, then we want to use [a-zA-Z].
  - [0-9] the string can contain any number 0-9.
  - [_\.-] the string can contain an undescore_, backslash\, period., or hyphen-. These are special characters and they are any non-alphanumeric characters, such as punctuation or symbols.
  - [\d] the string matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].

## Quantifiers
Quantifiers specify how many matches has to be made in each group indicated by the (). More on that later. In our example, there are 2 quantifiers - the plus+ and {2,6}
  - + indicates that that group has to match one or more times.
  - {2,6} or {n, m} indicates that that group has to match from n to m times. So in our case, this string has to contain 2 characters and no more than 6 characters.

There are different types of quantifiers. Take a look at the table in the link below to see more. 
https://docs.microsoft.com/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions

Quantifers are greedy, meaning they match as many occurrences of particular patterns as possible. You can make them lazy by adding a question mark?, meaning it will match as few occurrences as possible.

<a name="grouping"></a>
## Grouping Constructs
Grouping Constructs are groups or sections defined by the parenthesis(). Each section within parentheses is known as a subexpression. We have 3 in our example.

<a name="or"></a>
## The OR Operator
The OR Operator defined as the pipe| is used to specify that the condition or characters before or after it should match. For example, we can write [a-z] as [a|b|c|d|e|....z].

<a name="escapes"></a>
## Character Escapes
A character escape defined by the backslash\ indicates that the character following it should be treated as special or "escaped." If you look at our example, the backslash\ in our first group means the special character can be used. 
But if you look at the backslash\ between group 2 and 3, it is outside the parenthesis and followed by a period. This means we literally want to use a period there. If you look at a standard email address, there a period in the domain name. i.e.  gmail.com or yahoo.com
Note: we do not need a backslash\ after the @ because it is not considered a special character.

<a name="classes"></a>
## Character Classes
Character classes define a set of characters, in which the input string should match.

Here are some of the other common character classes:
  .—Matches any character except the newline character (\n)

  \d—Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].

   \w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].

  \s—Matches a single whitespace character, including tabs and line breaks

We can do the inverse by capitalizing the letter. For example, \D matches a non-digit character.

## Flags
Flags are placed at the end of the regex to specify additional functionality or limits. There are 6 flags.
  -g: global search
  -i: case-insensitive search
  -m: multi-line seach
  -s: allows . to match newline character
  -u: "unicode"; treat a pattern as a sequence of unicode code points
  -y: perform a sticky search that matche starting at the currentt position in the target string.
  
 ## Author
  I am anspring coder studying the University of Washington. Graduating in Dec 2021. 
