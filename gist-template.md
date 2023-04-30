## Matching a Hex Value 

This tutorial will do it's best to analyze the expression /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ and it will attempt to break down it's corresponding components in an attempt to conceptualize how it matches hex values. I will do what I can to cover each part of the regex, try to articulate what it is attempting to do and provide specified examples of correspodning hex values that match the designated patern. 

## Summary

The designated regex I will give in this tutorial will be /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ which does in fact match hex values in different formats, allowing both 6-digit and 3-digit representations. A pattern will begin with a '#', which is an optional symbol. That optional symbol will either be followed by six, or three, hexadecimal characters. A regex such as this is often used for verifying and prying out hex color codes which can be used in several ways.

Here is a code snippet of this specific regex: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

## Table of Contents

- [Matching a Hex Value](#matching-a-hex-value)
- [Summary](#summary)
- [Table of Contents](#table-of-contents)
- [Regex Components](#regex-components)
  - [Anchors](#anchors)
  - [Quantifiers](#quantifiers)
  - [Character Classes](#character-classes)
  - [Flags](#flags)
  - [Grouping and Capturing](#grouping-and-capturing)
  - [Bracket Expressions](#bracket-expressions)
  - [Greedy and Lazy Match](#greedy-and-lazy-match)
  - [Boundaries](#boundaries)
  - [Back-references](#back-references)
  - [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Author](#author)

## Regex Components

### Anchors

The regex I will be using throughout this tutorial, once again is /^#?([a-f0-9]{6}|[a-f0-9]{3})$/. You can notice that it starts with the caret symbol, which kind of looks like the roof of a house, ^. The regex ends with a $ symbol and my bet is mostly anyone can conceptualize that one easily. These symbols, at the beginning, and end are called anchors and they keep an eye out to make sure the regex matches the entire string rather than only matching certain parts of it. The ^ symbol, which I called the roof, is the start, once again and the $ symbol is the end with a slash preceeding the first sybol and following the last. These are called anchors and they make sure the regex pattern complies the with hex value, in it's entirety. 

An example for this would be that this matches #a3c8f0, but it does not match #a3c8f0.

### Quantifiers

The formerly mentioned regex, to be used throughout this tutorial uses things referred to as quantifiers. These quantifiers designate the amount of times a specific pattern occurs. So in our regex {6} and {3} are used to show that the preceeding character group, the symbols that preceed those curly braces appear either six, or three times. The character groups, a-f for instance, represent lowercase letters while 0-9, the second character group, represents any digit being used under ten. 

An example here would be that the regex matches #a3c8f0, and #abc, but it will not match #a3c8f09.

### Character Classes

The character classes, like the ones mentioned in the "Quantifiers" section are indicated by the symbols, [], where the regex is contained. Inside those symbols the character classes set what single characters can match within those assigned rules. As mentioned in the "Quantifiers" section, our specifications are lower case letters and any digit under ten. 

An example of this would be a matching of #a3c8f0 and #1b2, but not a match of #g8h1j2.



### Flags

In what are referred to as regular expressions flags are used often in order to step in and be the mediator when it comes to regex patterns matching up. These flags are added after the closing delimeter, which makes boundaries clear in many applications, in this case how the pattern is applied and the regular expression as mentioned earlier in this section. 

The following are some widely used flags:

A g flag. This is also called a global flag and it permits the regex to match any occurnece of a pattern within an input string instead of simply pumping the breaks at the first match.

An i flag. This is also called an ignore case flag and it's easy to understand what it's aim is, given it's title. For instance if you wanted any letter to be used, upper or lower case you would use this flag to ignore an only lower case designation, in the regex as an example. 

An m flag. Also referred to as a multiline flag. This flag changes how the anchors act in order to ensure the beginning and ending of each line are matched, within a multiline string. 

An s flag. Also called a dot all flag, which would not be your first guess given the letter that is associated with the flag. This ensures, if the user so designates, that all characters match which most certainly is not the default way of operating when it comes to regex's.

A u flag. This is called a unicode flag. This simply allows for unicode matching which means that hexidecimal numbers that you want to match will in fact match.

So in our regex we've been using, once again /^#?([a-f0-9]{6}|[a-f0-9]{3})$/, the user of this tutorial may notice there are no assigned flags. It is possible that some flags can be the default setting, so it is always prudent for the user to check for this. 

An example to consider would be using our designated regex with any form of Javascript. 

So an input of #a3c8f0 matches #a3c8f0 because in Javascript the g flag is on by default. This means the regex can match what are called multiple occurences. Flags serve to give the user more control over their regex in order to get exactly what they want out of it. 

### Grouping and Capturing

In our regex, the parantheses are in there in order to group and capture. The pattern inside the parantheses is referred to as a group. This allows us, as users, to apply quantifiers as we see fit. We can vary things up as much as we'd like. 

An example for this section would be that our regex will match #a3c8f0 while simultaneously capturing the hex value, which  is a3c8fo, as a group. 

Our first group would be [a-f0-9]{6}.

So, in the above group, you can match a sequence of six characters, as designated by the number in the curly braces. 

Our second group would be Group 2: [a-f0-9]{3}.

In the second group you can match a sequence of three characters following the same logic from above. 

So, our regex, /^#?([a-f0-9]{6}|[a-f0-9]{3})$/, with an input of #a3c8f0, matches #a3c8f0. An example of a capture from the first group would be a3c8f0. Tools or programming languages may vary how you, the user, accesses the captured group. 



### Bracket Expressions

Next we will cover Bracket Expressions, which are represented by the symbols, []. Bracket Expressions allow us, as user's, to assign designated values or character's that can be expressed while allowing the regex to match it. In our regex our character class [a-f0-9] is utilized inside our groups. As previously mentioned only lowercase letters or digits under ten will match up. 

An example we can use, here in this section is that #a3c8f0 and #1b2 will match, but #g8h1j2 will not. 

### Greedy and Lazy Match

In our expressions we referred to earlier as regular expressions our quantifiers are what are what is called greedy, which is the default setting here, so to speak. This greed comes in the form of matching as many occurences as is possible, very greedy indeed. This is not always a good thing though. Which brings me to my point and the title of this section, "Greedy and Lazy Match". Given our coding definition of greedy you can probably guess what Lazy Match is, in this context. 

In our regex, the quantifiers {6} and {3} are in fact greedy. They match six and three occurences of the designated character group. Lowercase numbers and digits under ten. 

In order to have the quantifiers be lazy you can add the question mark symbol after them. This designates them to be lazy instead of greedy which can be what the user needs, depending on the given situation. 

Our regex: /^#?([a-f0-9]{6}|[a-f0-9]{3})?$/

So for our example in this section we will input #abc #123 which will match #abc. Because of the question mark symbol we only matched #abc instead of #abc #123, which would have been greedy.

Lazy matching can come in handy when you want a shorter substring that still lines up with your regex pattern. The default setting is greedy but you can always change this. 

### Boundaries

In regular expressions, boundaries allow you to specify specific positions within a string. They are not actual characters but rather assertions that enforce certain conditions regarding the positions in the text. The two most commonly used boundaries are the caret ^ and the dollar sign $.

The caret ^ asserts that the regex pattern must match at the beginning of the string. In the regex /^#?([a-f0-9]{6}|[a-f0-9]{3})$/, the caret ^ is used at the start of the regex to enforce that the matching hex value must begin at the beginning of the string. If the caret is not present, the regex would match a hex value anywhere within the string.

Example: Consider the regex /^#?([a-f0-9]{6}|[a-f0-9]{3})$/.

Input: #a3c8f0
Matches: #a3c8f0
In this example, the regex matches #a3c8f0 because it begins with the specified hex value. If the input were text #a3c8f0, the regex would not match because the hex value is not at the beginning.

The dollar sign $ asserts that the regex pattern must match at the end of the string. In the regex /^#?([a-f0-9]{6}|[a-f0-9]{3})$/, the dollar sign $ is used at the end of the regex to ensure that the matching hex value ends at the end of the string. Without the dollar sign, the regex would match a hex value even if there are additional characters following it.

Example: Using our regex /^#?([a-f0-9]{6}|[a-f0-9]{3})$/.

Input: #a3c8f0
Matches: #a3c8f0
In this example, the regex matches #a3c8f0 because it ends with the specified hex value. If the input were #a3c8f0 text, the regex would not match because there are additional characters after the hex value.

By using the caret ^ and the dollar sign $ in the regex, you can ensure that the hex value matches the entire string and is positioned at the start and end.


### Back-references

In regular expressions, back-references allow you to refer back to a previously captured group within the regex pattern. This allows you to match the same content that was previously captured, enabling you to find repeated patterns or enforce consistency in the text.

Back-references are represented using the backslash \ followed by a number. The number corresponds to the order of the capturing group. In the regex /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/, the back-reference \1 is used to refer back to the opening tag captured in the first capturing group ([a-z]+).

Example: Consider the regex /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/.

Input: <div>Hello, World!</div>
Matches: <div>Hello, World!</div>
Group 1 Capture: div
In this example, the opening tag <div> is captured by the first capturing group ([a-z]+). The back-reference \1 is then used to ensure that the closing tag </div> matches the same tag name as the opening tag. This enforces that the same tag is used for both opening and closing.

Back-references are particularly useful when dealing with repeated patterns, such as matching paired HTML tags or finding duplicated words.

Example: Consider the regex /(\b\w+)\s+\1/.

Input: hello hello world
Matches: hello hello
Group 1 Capture: hello
In this example, the capturing group (\b\w+) captures a word, and the back-reference \1 ensures that the same word is repeated again in the text. This regex would match the repeated word "hello" in the input "hello hello world".

By using back-references, you can refer back to previously captured groups and enforce consistency or find repeated patterns within the text.


### Look-ahead and Look-behind

Look-ahead and Look-behind are techniques used in regular expressions that give the user the ability to include conditions as they see fit, either in front of, or after the current position but the user doesn't have to include those conditions they specified in the actual match. These conditions are referred to as zero-width assertions and they are called that because they do not consume any characters throughout the matching process. 

Look-ahead, which is represented by (?=...), in which the dots signifies the pattern that will be matched ahead (Look-ahead) of the current position. 

Look-behind, which is represented by (?<=...), in which the dots represent the pattern to be matched behind (Look-behind) the current position.

In the following regex, which is a new one, /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/, both features, Look-ahead/behind are used specify conditions related to the url structure. By inputing https://www.example.com the user will in fact get a match with https://www.example.com. Here the look-ahead is used to ensure that the URL must start with either http://, or https://. It will not used any characters in the match but it makes certain those URL protocols are used. In the next example the look-behind will be used to make sure that the domain name used the protocol. 

In our regex for this section, ^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/, we can input www.example.com which will match www.example.com because the input does not start with http://, or https://. The regex still manages to match the url. In this case the look-ahead condition is optional which allows the URL's to be used without the protocol. 

Both features are highly usedful tools, so to speak, that will enable the user to validate conditions they specify, either ahead of or behind the current postion in the text. They indeed are highly flexible and exert control over the matching process as the user sees fit to apply them. 



## Author

[William Hirst](https://github.com/FreeWill201)

My name is William Hirst. The link to my Github Profile is listed above. I am a part time Full Stack Web Dev student in a Coding Bootcamp through Rutgers University. I am also a graduate of Rutgers with a BA in Psych. My educational journey has been a diverse one in which I have met tons of people from all different perspectives in life. I am lucky to have the experience I do and I hope you enjoyed my tutorial and found it's format practical and applicable. Thank you and have a great day. 