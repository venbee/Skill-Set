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

### Summary
- there are three stages in text analytics:
- - Lexical processing
- - Syntactic processing
- - Semantic processing

- anchor characters (^ and $) and the wildcard (.)
- The ^ and $ operator match the start and end of the string.
- The re.match() function looks for the given pattern at the very start. If it doesn’t find a string at the very start of the string, it returns None.
- The quantifier {0,} will match the preceding character zero or more times. This is equivalent to what the ‘*’ does as it also matches the preceding character zero or more times.
- The correct syntax of the re.sub() function is re.sub(pattern, replacement, string)
-  ‘\s’ captures all the whitespaces in a given string.
- ‘\’ escapes the meaning of the character that follows it in a regular expression pattern.

# Basic Lexical Processing

- Corpus is just a name to refer to textual data in NLP jargon.
- How to preprocess text using techniques such as
- - Tokenisation
- - Stop words removal
- - Stemming
- - Lemmatization

- How to build a spam detector using one of the following models:
- - Bag-of-words model
- - TF-IDF model

- The most basic statistical analysis you can do is to look at the word frequency distribution, i.e. visualising the word frequencies of a given text corpus.
-  the Zipf's law (discovered by the linguist-statistician George Zipf) states that the frequency of a word is inversely proportional to the rank of the word, where rank 1 is given to the most frequent word, 2 to the second most frequent and so on. This is also called the power law distribution.
- The Zipf's law helps us form the basic intuition for stopwords - these are the words having the highest frequencies (or lowest ranks) in the text, and are typically of limited 'importance'.
- there are three kinds of words present in any text corpus:
- - Highly frequent words, called stop words, such as ‘is’, ‘an’, ‘the’, etc.
- - Significant words, which are typically more important to understand the text
- - Rarely occurring words, which are again less important than significant words
- Generally speaking, stopwords are removed from the text for two reasons:

- They provide no useful information, especially in applications such as spam detector or search engine. Therefore, you’re going to remove stopwords from the spam dataset.

- Since the frequency of words is very high, removing stopwords results in a much smaller data as far as the size of data is concerned. Reduced size results in faster computation on text data. There’s also the advantage of less number of features to deal with if stopwords are removed.
- Rank of a word is the ordered index of the word in the word list.

### Tokenization
- machine learning works on numeric data, not text.
- you will extract features from the messages. From each message you’ll extract each word by breaking each message into separate words or 'tokens'.
- tokenisation - a technique that’s used to split the text into smaller elements. 
- These elements can be characters, words, sentences, or even paragraphs depending on the application you’re working on.
- In the spam detector case, you will break each message into different words, so it’s called word tokenisation
- other types of tokenisation techniques such as character tokenisation, sentence tokenisation, etc. Different types of tokenisation are needed in different scenarios.
- In NLTK, you also have different types of tokenisers present that you can use in different applications.
- The most popular tokenisers are:
- - Word tokeniser splits text into different words.
- - Sentence tokeniser splits text in different sentence.
- - Tweet tokeniser handles emojis and hashtags that you see in social media texts
- - Regex tokeniser lets you build your own custom tokeniser using regex patterns of your choice.

### Bag-of-words Representation
- how to represent text in a format that you can feed into machine learning algorithms.
- The most common and most popular approach is to create a bag-of-words representation of the text data that you have. The central idea is that any given piece of text, i.e., tweets, articles, messages, emails etc., can be “represented” by a list of all the words that occur in it (after removing the stopwords), where the sequence of occurrence does not matter. You can visualise it as the “bag” of all “words” that occur in it.
- you need to represent all the bags in a matrix format, after which you can use ML algorithms such as naive Bayes, logistic regression, SVM etc., to do the final classification.
- Each document sits on a separate row and each word of the vocabulary has a its own column. These vocabulary words are also called as features of the text.
- The bag-of-words representation is also called bag-of-words model but this is not to be confused with a machine learning model. A bag-of-words model is just the matrix that you get from text data.
- The frequency approach is slightly more popular and the NLTK library in Python also fills the bag-of-words model with word frequencies rather than binary 0 or 1 values.
- keeping the two separate is actually going to hinder the performance of the machine learning algorithm since it is redundant information. Also, this redundancy is going to increase the number of features due to which the classifier can face the curse of dimensionality (error increases with the increase in number of features). To get rid of this problem, you’re going to learn two more preprocessing techniques - stemming and lemmatization

### Stemming and Lemmatization
- Stemming makes sure that different variations of a word, say ‘warm’, warmer’, ‘warming’ and ‘warmed,’ are represented by a single token - ‘warm’, because they all represent the same information (represented by the 'stem' of the word).
- Another similar preprocessing step (and an alternative to stemming) is lemmatisation. 
- the repeated tokens or features were nothing but a variation or an inflected form of the other token. 
- The two techniques that you just learnt reduce these inflected words to the original base form.
- Stemming
- - It is a rule-based technique that just chops off the suffix of a word to get its root form, which is called the ‘stem’.
- Porter stemmer: This was developed in 1980 and works only on English words. 
- Snowball stemmer: This is a more versatile stemmer that not only works on English words but also on words of other languages such as French, German, Italian, Finnish, Russian, and many more languages. 
- Lemmatization
- - This is a more sophisticated technique (and perhaps more 'intelligent') in the sense that it doesn’t just chop off the suffix of a word. Instead, it takes an input word and searches for its base word by going recursively through all the variations of dictionary words. The base word in this case is called the lemma.
- The most popular lemmatizer is the WordNet lemmatizer created by a team of researchers at the Princeton university.
- A stemmer is a rule based technique, and hence, it is much faster than the lemmatizer
- stemmer typically gives less accurate results than a lemmatizer.
- A lemmatizer is slower because of the dictionary lookup but gives better results than a stemmer.
- for a lemmatizer to perform accurately, you need to provide the part-of-speech tag of the input word
-  the Porter stemmer and the Snowball stemmer. Snowball stemmer works a little better, but usually, you won’t see much of a difference as both of them are rule based. 

### Final Bag-of-words representation
- Lemmatization only works on correctly spelt words.
### TF-IDF Representation
- The term TF stands for term frequency
- the term IDF stands for inverse document frequency.
- The TF-IDF representation, also called the TF-IDF model, takes into the account the importance of each word.
- Higher weights are assigned to terms that are present frequently in a document and which are rare among all documents. On the other hand, a low score is assigned to terms which are common across all documents.
- The idf of a term is the log of the total number of documents divided by the total number of documents where the term appears. Now, the total number of documents where the term is present is a constant and so is the total number of documents. Hence, idf is also a constant for a given word.

- Words less than a certain threshold are removed to eliminate special characters such as double exclamation marks, or double dots (the period character). And you won’t lose any information by doing this because there are no words less than two characters other than some stopwords (such as ‘am’, ‘is’, etc.).

## Advanced Lexical Processing
- Phonetic hashing and the Soundex algorithm to handle different pronunciations of a word
- The minimum-edit-distance algorithm and building a spell corrector 
- Pointwise mutual information (PMI) score to preserve terms that comprise of more than one word

- Canonicalisation means to reduce a word to its base form (Stemming and Lemmatization).
- Stemming tries to reduce a word to its root form. Lemmatization tries to reduce a word to its lemma. The root and the lemma are nothing but the base forms of the inflected words.
- To deal with misspellings, you’ll need to canonicalise it by correcting the spelling of the word.
- To deal with different spellings that occur due to different pronunciations, you’ll learn the concept of phonetic hashing which will help you canonicalise different versions of the same word to a base word.
- Phonetic hashing buckets all the similar phonemes (words with similar sound or pronunciation) into a single bucket and gives all these variations a single hash code.
- Phonetic hashing is done using the Soundex algorithm. American Soundex is the most popular Soundex algorithm. It buckets British and American spellings of a word to a common code. It doesn't matter which language the input word comes from - as long as the words sound similar, they will get the same hash code.
- Words with different pronunciations tend to have same consonant sounds but different vowels and ‘H’, ‘Y’ and ‘W’ sounds. Hence, they are not the identity of the words. The consonants are the real identity of the words except for the consonants ‘H’, ‘Y’ and ‘W’.
- An edit distance is a distance between two strings which is a non-negative integer number.
- edit distance is the number of edits that are needed to convert a source string to a target string.
-   Insertion of a letter in the source string. To convert ‘color’ to ‘colour’, you need to insert the letter ‘u’ in the source string.
- Deletion of a letter from the source string. To convert ‘Matt’ to ‘Mat’, you need to delete one of the ‘t’s from the source string.
- Substitution of a letter in the source string. To convert ‘Iran’ to ‘Iraq’, you need to substitute ‘n’ with ‘q’
- The statement is correct. It doesn't matter which is the source string and which is the target string while calculating the edit distance.
- The Damerau–Levenshtein distance, apart from allowing the three edit operations, also allows the swap (transposition) operation between two adjacent characters which costs only one edit instead of two.
- This edit operation was introduced because swapping is a very common mistake. For example, while typing, people mistype ‘relief’ to ‘releif’. This has to be accounted as a single mistake (one edit distance), not two.
- A spell corrector is a widely used application that you would see almost everywhere on the internet.
- Spell correction is an important part of lexical processing. 
- The known() function filters out the valid English word from a list of given words. It uses the frequency distribution as a dictionary that was created using the seed document. 
-  the function possible_corrections() returns a list of all the potential words that can be the correct alternative spelling.
- pointwise mutual information, also called the PMI
- involves identifying seperate terms and representing them as a single token.
- After calculating the PMI score, you can compare it with a cutoff value and see if PMI is larger or smaller than the cutoff value. A good cutoff value is zero. Terms with PMI larger than zero are valid terms, i.e. they don’t need to be tokenised into different words.
- 