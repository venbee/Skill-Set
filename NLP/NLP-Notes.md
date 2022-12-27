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
