# Regex: Matching a Hex Value

I'm writing this gist to teach myself more about regular expressions (regex). After having done some research, I have chosen a regex to explore.
I'm going to break-down this regex piece by piece and explain each component. If you're reading this and you are not one of the central graders at EDX, hopefully you will learn something too.

## Summary

The below string of characters is a regex that is used to match a hexidecimal value. For those that don't know, in programming, a hex code is a six character code that represents a color.

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

This gist will break this regex down and explain how it works. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)

## Regex Components

This regex contains anchors (boundaries), bracket expressions, quantifiers, an OR operator, and quantifiers. Also, a regex is considered to be a literal, so it must be wrapped in forward slash characters (/).

### Anchors

The ^ symbol and $ symbol in the regex are anchors. According to the EDX bootcamp blog, 
"The ^ anchor signifies a string that begins with the characters that follow it", and "The $ anchor signifies a string that ends with the characters that precede it".
You can think of these anchors as boundaries. They define where the string begins and where it ends, as well as what the beginning must start with and what the end must end with. 

### Quantifiers

Quantifiers limit the string that your regex can match. We can see multiple examples of quantifiers in this regex. We will start with the numbers in the curly brackets. The {6} and the {3} limit how many characters 
a matching string can contain. {6} for example, means that your string must contain 6 characters. Hexidecimal codes and be 6 characters long, but if written short-hand, they can be 3 characters long (#ffffff can be written as #fff).
This is why we see both {6} and {3} in the regex, because it ban be 6 or 3 characters long. 

The '?' symbol is also a quantifier. The '?' indicates that there are zero or one occurences of the preceding element. Hexidecimal codes might start with a # symbol, but they also might not.
So the inclusion of the '?' symbol will allow the regex to match both '#ffffff' and 'ffffff', or '#fff' and 'fff'.

### OR Operator

The OR operator is represented by the '|' symbol. It is pretty self explainatory. In this case, it is used to allow the regex to match with a string that contains lowercase letter a through f, numbers 0 through 9, and is 6 characters long,
or a string that contains lowercase letter a through f, numbers 0 through 9, and is 3 characters long.

### Bracket Expressions

There are two bracket expressions in this regex, both represented by [a-f0-9]. This means that a matching string can contain lowercase letters a through f and numbers 0 through 9.

### Greedy and Lazy Match

According to the EDX Bootcamp Blog, "Quantifiers are inherently greedy, meaning they match as many occurrences of particular patterns as possible". "Each of these quantifiers can be made lazy by adding the ? symbol after it, meaning it will match as few occurrences as possible".
The only lazy match in this regex is to the pound symbol (#).

### Boundaries

Boundaries were covered in the anchor section.

## Author

My name is Ben Whann and I am an aspiring software engineer. Here is a link to my GitHub profile, feel free to take a look: https://github.com/BenWhann
