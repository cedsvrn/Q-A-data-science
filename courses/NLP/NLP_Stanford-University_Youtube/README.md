# NLP Stanford University course
https://www.youtube.com/watch?v=oWsMIW-5xUc&list=PLLssT5z_DsK8HbD2sPcUIDfQ7zmBarMYv


## Course 1 : Introduction
**Mostly solved :**
- Spam detection
- Part-of-speech (POS) : Saying "blue" is an adjective, "drink" is a verb ...
- Named entity recognition (NER) : Saying "Einstein" is a person, "Paris" is a localisation ...

**Making good progress :**
- Sentiment analysis
- Coreference resolution
- Word sense disambiguation (WSD) : knowing if mouse is an item or an animal
- Parsing
- Machine translation (MT)
- Information extraction : "You're invited in Paris, Sunday 10th february at 10:45" -> "Paris", "Sunday 10th february", "10:45"

**Still really hard :**
- Question answering (QA)
- Paraphrase : saying the same thing with other words
- Summarization
- Dialog

**What makes NLP hard :**
- Ambiguity : knowing wich word is a verb, noun, in specific sentences.
- Non-standard engish
- Segmentation (parsing) issue : New York
- Idioms
- Neologisms : unfirend, retweetk, bromance

--> Probabilistic models with text features

**Course Program :**
- Viterbi
- Naive Bayes, Maxent Classifiers
- N-gram language modeling
- Statistical Parsing
- Inverted index, tf-idf, vector models of meaning
- Information extraction
- Spelling correction
- Information retrieval
- Sentiment analysis

## Course 2 : Regular expressions

**Formal language for specifying text strings.**

- Train : https://www.regexpal.com/

Disjunctions :
- **[] = Any letters in this square brackets**
    - [1234567890] = any digit
    - [wW]ood = "Wood" OR "wood"
- **Quite anoying to use, so --> Ranges : [A-Z]**
    - [A-Z] : An upper case letter
    - [a-z] : A lower case letter
    - [0-9] : Any single digit
    - [A-Za-Z] : Any uppercase or lowercase letter
    - [ !] : Matching with space or !

- **^ = NOT**
    - [^A-Z] = All the non upercase caracters
    - [^e^] = Neither e nor ^

- **| = OR**
    - yours|mine = "yours" OR "mine"
    - Warning : yours|mine != [yours|mine]
        - First will search for yours" OR "mine"
        - Second will search for any letter in "yours" OR any letter in "mine"
    - [gG]round|[wW]ood = "ground" or "Ground" or "wood" or "Wood"

- **? = optional previsou char**
    - colou?r = "color" OR "colour"

- **\* = zero or more of previous char**
    - oua*h! = "ouh!" OR "ouah!" OR "ouaah!" OR "ouaaah!" OR "ouaaaaaah!" ...

- **+ = one or more of previous char**
    - oua+h! = "ouah!" OR "ouaah!" OR "ouaaah!" OR "ouaaaaaah!" ...
    - baa+ = "baa" OR "baaa" OR "baaaa" ...

- **. = Any carac**
    - beg.n = "begin", "begun", "beg6n", "beg!n"

- **^[] = Begining of the line**
    - ^[A-Z] = Capital letter at the beginning of the line

- **[]$ = End of the line**
    - [a-z]$ = Lowercase letter at the end of a line
    - !$ = "!" At the end of a line

- **\ = cancelling effect**
    - \. = All the "."

**False positive = Type 1**
    - Matching strings that we should not match
    - Example : When looking for all the "the" and "The" in a sentence : finding "other", "therefore" ...
**False negative = Type 2**
    - Not matching string we should have matched
    - Example : When looking for all the "the" and "The" in a sentence : not finding "The"

**Reducing the errors =**
- Increasing accuracy or precising (minimizing false positive)
- Incresing coverage or recall (minimizing false negatives)

## Course 3 : Regular expressions in NLP

**Tokenizer :**
Lexer = tokenizer

Regexp are used in tokenizers to parse the text.

Mediu article on subject : https://towardsdatascience.com/dynamic-word-tokenization-with-regex-tokenizer-801ae839d1cd

## Course 4 : Word tokenization

**Every NLP task need to do text normalization :**
1 - Segmenting/tokenizing words in running text
2 - Normalizing word formats
3 - Segmenting sentences in running text

**How many words in a sentence ?**
- Depends of the definition of "word"
- Do we use lemma ? Meaning cats and cat counts as 1
- N = number of tokens
- V = vocabulary = set of types

**Issue in tokenization :**
- what're, I'm, isn't --> What are, I am, is not
- state-of-the-art --> state of the art ?
- San Francisco --> One or two token ?
- Chinese and Japanese : No spaces between words
- Japan : multiple alphabets

Work tokenization = Word Segmentation

**Maximum matching Word segmentation Algorithm used for Chinese (Greedy) :**
1 - Start with the first letter of the word
2 - Find the longest matching word in the dictionnary
3 - End the word and start again at 2

--> not good in English
--> Greedy works well in Chinese but probabilistic segmentation algorithms work even better

