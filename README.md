# EX-06 Implementation of Semantic Analysis
### Aim: 
To perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques.
### Algorithm:
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.
### Program:
**Developed By: NIVETHA A**

**REGISTER NO:212222230101**
##### Importing NLTK and Resource Downloads
```Python
import nltk
nltk.download( 'punkt' )
nltk.download('wordnet')
nltk.download('omw-1.4')
from nltk.tokenize import word_tokenize
nltk.download( 'averaged_perceptron_tagger' )
from nltk.corpus import wordnet
```
##### Tokenization and Part-of-Speech Tagging
```Python
sentence=input()
words = word_tokenize(sentence)
pos_tags= nltk.pos_tag(words)
for word, tag in pos_tags:
    print(f"{word:<6} - {tag}")
```
##### Extracting Synonyms and Antonyms from Words
```Python
synonyms =[]
antonyms =[]
for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append (lemma.name())
            if lemma.antonyms():
                antonyms.append (lemma.antonyms()[0].name())
print ( "Synonyms : " ,set(synonyms))
print ( "Antonyms : " ,set(antonyms))
```

### Output:
##### Parts of Speech:
![380979313-88785faf-6d00-4e39-9436-4e6cacbc5b78](https://github.com/user-attachments/assets/035bb2b0-17c3-488d-8670-e191d77d35d8)

##### Synonyms and Antonyms:
![380979363-5cf3fab4-8648-46b3-b4e2-46591bf0a204](https://github.com/user-attachments/assets/667ce329-13b2-4ede-8cd3-c06d7aedf443)


### Result:
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.<br>

