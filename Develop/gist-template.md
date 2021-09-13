# Regex Tutorial - E-Mail

What does regex mean, you ask? Well, it's short for regular expression. These expressions are used for things like validations, extractions, and even search/find & replace functionalities. They can be used in many different programming languages.

How does it work?
A Regex is an organized series of characters that define a search pattern. Yes, this is pretty broad but this allows unlimited customization based on your specific goals.

## Summary
This is a basic regex used for matching an email address. We'll walk through each of the components next.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This is a good one to talk about because email validation is a very common practice among developers writing code, and on the user end is a known hassle/necessary process of pretty much anyone who has an internet connection.

This tutorial was written using https://regexr.com/.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
In our example, take a look at the outer characters between the beginning and end /slashes/ ("^" and "$"). This represents the beginning and end of a string. These characters are used regularly in regex. Since an email address is a single string, we have a single start and end. 

### Quantifiers
Even though we have a single string, we do have three types of data. 
First the email "username", second the email service, and third the ".com"
(foobar) (@email) (.com)

Quantifiers are used to connect & validate these datatypes seperately within our single string. 
The first quantifier in our example "+" means "1 or more". More specifically, one or more characters within the first data set.
([a-z0-9_\.-]+)
The second quantifier within the third data set "{}" means {min/max}. Our code means data set 3 should be between 2 and 6 characters long.
([a-z\.]{2,6})

### Character Classes
Characters include:
. (any character except newline)
\w\d\s	(word, digit, whitespace)
\W\D\S	(not word, digit, whitespace)
[abc]	(any of a, b, or c)
[^abc]	(not a, b, or c)
[a-g]	(character between a & g)

The first data set has an example. ([a-z0-9_.-]+) 
The "." using the above reference means "any character except newline". and it's followed by a "-" to indicate that the period is not a part of the data set.

Looking at the rest of the regex, we have another character class "\d" meaning look for a digit(0-9). 

### Grouping and Capturing

If you didn't notice before, each of our data sets or capturing groups are contained within parentheses(). This establishes a group that defines a combination of search parameters.
([a-z0-9_\.-]+)
([\da-z\.-]+)
([a-z\.]{2,6})

### Bracket Expressions
Bracket expressions "[]" are used to contain machable characters. 
([a-z0-9_\.-]+)
This one defines the parameters as any lower-case letters, any numbers, and the "_" underscore symbol. 

### Greedy and Lazy Match
These allow can allow us to custimize the our overall search by being greedy (include all characters for matching purposes) or lazy (match only these characters). 
We use "+" and "{}" which are both considered greedy so consider all characters in set. 

## Author

Written by Mariah Eckrich @ https://github.com/meck512 
