# Matching a Hex Value Using Regex

This file will explain how we can use regular expression to match HEX values.
The hexadecimal (HEX) system is a number system that uses 16 symbols or digit values from 0-9 which are followed by 6 possible letters: A, B, C, D, E, and F, which represent values from 10-15. Hex values can therefore represent large binary numbers using fewer digits.

## Summary

We will describe the following regex: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ 

This regular expression uses anchors, quantifiers, OR Operators, grouping, capturing, and bracket expressions. An in-depth examination of these components can be found below. 

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
Anchors include both the ^ and $ characters. In our Regex, we use both of these anchors:
/^#....$/ 

In this case, the ^ anchor represents a string that begins whatever characters following it. For instance, ^Hey would find strings that begin with "Hey". In our case, ^# will find strings that begin with "#". 
The $ anchor represents a string that ends with the characters preceding it. For example, etc$ would find strings that conclude with "etc". In our case, the ^ and $ anchors work together to ensure that our results match the entire pattern from beginning (^ on) to end (before $).

### Quantifiers
Quantifiers establish the limits of the string that our regex matches. Quantifiers match as many occurrences of specific patterns as possible. 

In our regex, we use the {} quantifier to set our limits for a match. {6} and {3} from our regex will limit our results to ones that match the pattern exactly 6 or 3 times, respectively. 

Our regex snippet: [a-f0-9]{6} and [a-f0-9]{3}
In our case, [a-f0-9]{6} will match patterns with letters A-F, a-f, or digits from 0-9 with a length of 6. Similarly, [a-f0-9]{3} will match patterns with letters A-F, a-f, or digits from 0-9 with a length of 3. 


Our regex also uses the ? quantifier, which matches the pattern either 0 or one time. Having ? follow the # symbol in our regex means that we will search for patterns that either do or do not use the # symbol (i.e., the # symbol is optional). 

### OR Operator
Bracket expressions do not require the results to match all of the pattern's requirements. 
OR Operator: |
Our regex snippet: [a-f0-9]{6}|[a-f0-9]{3}

In this case, the | indicator divides our big expression [a-f0-9]{6}|[a-f0-9]{3} into two parts: [a-f0-9]{6} and [a-f0-9]{3}. This means that our regex will find matches for either of these two expressions.
Specifically, our regex could find strings of 6 characters containing a-f and/or integers between 0-9; as well as strings of 3 characters containing a-f and/or integers between 0-9.

### Grouping and Capturing
Grouping is done to ensure that different parts of a string can fulfill different requirements by breaking them up into sections.
Primarily, parentheses (()) are used to group a section of reges. In our expression, we use parentheses to block off this section: ([a-f0-9]{6}|[a-f0-9]{3}). Therefore, the opening parenthesis ( represents the beginning of the group, and the closing parenthesis represents the end of the group.


### Bracket Expressions
Square brackets enclose a range of characters that we want to include. Our expression has two sets of square brackets: [a-f0-9]. 
[a-f] indicates that the string can only contain lowercase letters a-f.
[0-9] indicates that the string can only contain the numbers 0-9. 

Altogether, [a-f0-9] will match any string that includes any combination of lowercase letters a-f and and number between 0-9, and these characters can appear in any order. Note that the string is not required to meet all of the requirements in our case. 

## Author

Hi, I'm Petra, an aspiring full-stack developer. Check out my work on GitHub: https://github.com/poorlybicycle !