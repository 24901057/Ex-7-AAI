<H3>NAME : Thejashree S </H3>
<H3>REGISTER NO: 212224240175</H3>
<H3>EX. NO.9</H3>
<H3>DATE: 03.09.26</H3>
<H1 ALIGN =CENTER>Implementation of Text  Summarization</H1>
<H3>Aim: to perform automatic text summarization using Natural Language Processing (NLP) techniques. </H3> 
 <BR>
<h3>Algorithm:</h3>
Step 1 Import necessary libraries for natural language processing tasks.<BR>
Step 2: Download NLTK resources, including the punkt tokenizer and stopwords.<BR>
Step 3: Define Text Preprocessing Function to tokenize, remove stopwords, and perform stemming.<BR>
Step 4: Define the Text Summarization Function using a simple frequency-based approach.<br>
    - Calculate the frequency of each word in the preprocessed text.<br>
    - Calculate a score for each sentence based on the sum of word frequencies.<br>
    - Select the top N sentences with the highest scores to form the summary.<br>
Step 5: Construct the main program to read the paragraph  and perform text summarization<br>
      - Generate and print the original text.<br>
      - Generate and print the text summary using the  Text Summarization function<br>
<H3>Program:</H3>

```.PY
import nltk
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize, sent_tokenize

nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('stopwords')

def summarize(text, n=3):
    stop = set(stopwords.words('english'))
    words = [w.lower() for w in word_tokenize(text)
             if w.isalnum() and w.lower() not in stop]

    freq = nltk.FreqDist(words)
    sentences = sent_tokenize(text)

    scores = {
        s: sum(freq[w.lower()] for w in word_tokenize(s)
               if w.lower() in freq)
        for s in sentences
    }

    return ' '.join(sorted(scores, key=scores.get, reverse=True)[:n])


text = """Natural language processing (NLP) is a subfield of artificial intelligence.
NLP is used in chatbots, language understanding, and language generation.
NLP helps computers understand human language.
This program demonstrates text summarization using NLP."""

print("Original Text:\n", text)
print("\nSummary:\n", summarize(text))

```



<H3>Output</H3>

<img width="1695" height="441" alt="image" src="https://github.com/user-attachments/assets/c38ee851-c397-4038-a742-51768e371d6d" />


<H3>Result:</H3>
Thus ,the program to perform the Text summarization is executed sucessfully.
