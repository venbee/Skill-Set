# NLP Notes
NLP - Natural Language Processing
NLP also referred as text analytics

## Applications of NLP
- POS --> Parts Of Speech
- NER - named Entity Recognition
- Twitter opinion mining (unsupervised analysis)
- Semantics

## TEXT ANALYTICS: AREAS OF APPLICATION
- Banking and loan processing
- Insurance claim processing
- Customer relationship processing
- security and counter-terroism
- social media analytics
- computational social science
- E-commerce
- Psychology and cognitive service.

## Analytics on text is similar to sequence of words.

### Three Modules of Text Analytics
1) Lexical Processing
2) Syntactic Processing
3) Semantic Processing

1. Lexical Processing: 
Converting the raw text into words and depending upon application needs, converting into sentences and paragraphs as well.

2. Syntactic Processing: 
Extracting more meaning from the sentence by using its syntax (syntactic structures)

3. Semantic processing: 
Inferring the word's meaning to the collection of words that usually occur around it. By this, the machine should also be able to understand other semantic relations.

- Lexical and Syntactic Processing don't suffice when it comes to building advanced NLP applications such as language translation, chatbots etc. The machine after the above two processing steps will still be incapable of actually understanding the meaning of the text.

- In most of the applications, lexical and semantic processing simply form the pre-processing layer of the overall process. sometimes only lexical is used as pre-processing step.

1. Character Encoding:
A Unique code assigned to a character, based on the encoding standard, to represent it on a computer.

- We work with so many languages for our work other than english.
- In computers, the alphabets and special characters were to be converted to a numeric value before thay could be stored.
- Each character has a unique representation code on computers.
ASCII (American standard code for Information Interchange) was a widely popular standard that mostly encoded all English characters.
- The Unicode standard helps represent text in almost all the languages of the world.
    - UTF-16: Encodes each character with a 16-bit code.
    - UTF-8: Encodes each English character with an 8-bit code and each non-english character with a 32-bit code.

### Example Code
#### create a string
amount = u"₹50"
print('Default string: ', amount, '\n', 'Type of string', type(amount), '\n')

#### encode to UTF-8 byte format
amount_encoded = amount.encode('utf-8')
print('Encoded to UTF-8: ', amount_encoded, '\n', 'Type of string', type(amount_encoded), '\n')


#### sometime later in another computer
#### decode from UTF-8 byte format
amount_decoded = amount_encoded.decode('utf-8')
print('Decoded from UTF-8: ', amount_decoded, '\n', 'Type of string', type(amount_decoded), '\n')

## Regular Expressions
- Regular expressions, also called regex, are very powerful programming tools that are used for a variety of purposes such as feature extraction from text, string replacement and other string manipulations. 
- In order to become a master at text analytics, being proficient with regular expressions is a must-have skill.
- A regular expression is a set of characters, or a pattern, which is used to find substrings in a given string. 
- Learning regular expressions basically means learning how to identify and define these patterns.
- Regulars expressions are a language in itself since they have their own compilers. 

## Import re ## in Python usage
 - re.search() function returns a object if the pattern is found in the string.
 - match.start() and match.end() will return the index of the starting and ending position of the match found.
 - Quantifiers allow you to mention and have control over how many times you want the character(s) in your pattern to occur.
 - There are four types of quantifiers:
    - The ‘?’ operator
    - The ‘*’ operator
    - The ‘+’ operator
    - The ‘{m, n}’ operator
- The ‘?’  can be used where you want the preceding character of your pattern to be an optional character in the string. 
- A ‘*’ quantifier matches the preceding character any number of times.
- The ‘?’ matches the preceding character zero or one time. It is generally used to mark the optional presence of a character.
The ‘*’ quantifier is used to mark the presence of the preceding character zero or more times.
- The ‘+’ quantifier matches the preceding character one or more times. That means the preceding character has to be present at least once for the pattern to match the string.
- Thus, the only difference between '+' and '*' is that the '+' needs a character to be present at least once, while the '*' does not.
    - '?': Optional preceding character
    - '*': Match preceding character zero or more times
    - '+': Match preceding character one or more times (i.e. at least once)

- There are four variants of the quantifier that you just saw:
    - {m, n}: Matches the preceding character ‘m’ times to ‘n’ times.
    - {m, }: Matches the preceding character ‘m’ times to infinite times, i.e. there is no upper limit to the occurrence of the preceding character.
    - {, n}: Matches the preceding character from zero to ‘n’ times, i.e. the upper limit is fixed regarding the occurrence of the preceding character.
    - {n}: Matches if the preceding character occurs exactly ‘n’ number of times.
 
- Note that while specifying the {m,n} notation, avoid using a space after the comma, i.e. use {m,n} rather than {m, n}.

- An interesting thing to note is that this quantifier can replace the ‘?’, ‘*’ and the ‘+’ quantifier. That is because:

    - '?' is equivalent to zero or once, or {0, 1}
    - '*' is equivalent to zero or more times, or {0, }
    - '+' is equivalent to one or more times, or {1, }

- If you put the parentheses "()" around some characters, the quantifier will look for repetition of the group of characters rather than just looking for repetitions of the preceding character. This concept is called grouping in regular expression jargon.
- The escape sequence, denoted by a backslash ‘\’, is used to escape the special meaning of the special characters. To match a question mark literally, you need to use '\?' (this is called escaping the character).
- The '\' itself is a special character, and to match the ‘\’ character literally, you need to escape it too. You can use the pattern ‘\\’ to escape the backslash.
- if you want your regex to ignore the case of the text then you can pass the 're.I' flag. 
- you can have have a flag with the syntax re.M that enables you to search in multiple lines (in case the input text has multiple lines).
- You can pass all these flags in the re.search() function.
- re.search(pattern, string, flags=re.I | re.M)
- the re.compile() function. This function stores the regular expression pattern in the cache memory and is said to result in a little faster searches. You need to pass the regex pattern to re.compile() function.

#### without re.compile() function
- result = re.search("a+", "abc")

#### using the re.compile() function
- pattern = re.compile("a+")
- result = pattern.search("abc")

### Anchors and Wild Cards
- Anchors are used to specify the start and end of the string.
- The ‘^’ specifies the start of the string. The character followed by the ‘^’ in the pattern should be the first character of the string in order for a string to match the pattern.
- the ‘$’ specifies the end of the string. The character that precedes the ‘$’ in the pattern should be the last character in the string in order for the string to match the pattern.
- there is one special character in regular expressions that acts as a placeholder and can match any character (literally!) in the given input string. It’s the ‘.’ (dot) character is also called the wildcard character. 
- The wildcard comes handy in many situations. It can be followed by a quantifier which specifies that any character is present a specified number of times.

### Character Sets
- When we need to somehow specify that you are looking only for numerics and some other symbols, but avoid alphabets.
- To handle such situations, you can use what are called character sets in regular expression jargon.
- Character sets provide lot more flexibility than just typing a wildcard or the literal characters. Character sets can be specified with or without a quantifier. When no quantifier succeeds the character set, it matches only one character and the match is successful only if the character in the string is one of the characters present inside the character set.
- a character set is similar to a wildcard because it can also be used with or without a quantifier. It’s just that a character set gives you more power and flexibility!
- Note that a quantifier loses its special meaning when it’s present inside the character set. Inside square brackets, it is treated as any other character. 
- The ‘^’ has two use cases. You already know that it can be used outside a character set to specify the start of a string. Here, it is known as an anchor.
- It’s another use is inside a character set. When used inside a character set, it acts as a complement operator, i.e. it specifies that it will match any character other than the ones mentioned inside the character set.

### Meta Sequences
- There is a shorthand way to write commonly used character sets in regular expressions. These are called meta-sequences.
- You can either use them without the square brackets.
- you can them it inside the square brackets. For example, the pattern ‘[\w]+’ is same as ‘\w+’. But when you use meta-sequences inside a square bracket, they’re commonly used along with other meta-sequences. For example, the ‘[\w\s]+’ matches both alphanumeric characters and whitespaces. The square brackets are used to group these two meta-sequences into one.

### Greedy vs Non-Greedy
- when you specify the pattern 'ab{2,5}' to match the string 'abbbbb', it will look for the maximum number of occurrences of 'b' (in this case 5). This is called a 'greedy approach'.
- By default, a regular expression is greedy in nature.
- There is another approach called the non-greedy approach, also called the lazy approach, where the regex stops looking for the pattern once a particular condition is satisfied.

### RE Functions
#### re.match()
#### re.search()
#### re.findall()
#### re.finditer()
#### re.sub()

- The match function will only match if the pattern is present at the very start of the string. 
- The search function will look for the pattern starting from the left of the string and keeps searching until it sees the pattern and then returns the match.
- the re.sub() function. It is used to substitute a substring with another substring of your choice. 
- The result of the findall() function is a list of all the matches and the finditer() function is used in a 'for' loop to iterate through each separate match one by one.

### Grouping
- Sometimes you need to extract sub-patterns out of a larger pattern. This can be done by using grouping. 
- Grouping is achieved using the parenthesis operators. 
- Grouping is a very useful technique when you want to extract substrings from an entire match.
- 