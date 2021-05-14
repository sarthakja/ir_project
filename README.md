# Title recommendation for documents
This project recommends title of a document using extractive technique i.e. a sentence from the document is recommended as the title. 
## Preprocessing documents
Reuters data from the ntlk library is used and imported into the the memory. As the raw text for the documents also contains the title, the title is removed by finding the first newline character and removing the text till there. This new corpora is stored separatelty. After that the entire text is converted into lowercase, punctuations removed and tokenization applied to get the list of terms. Then porter stemming is used to obtain the normalized tokens. This is the tokenization technique used for the entire project.
## Getting IDF values
TfidfVectorizer from sklearn has been used to get idf values of the terms. This needs preprocessing, which involves, tokenizing the documents, using above technique and removing stopwords. After getting the idf values, a dictionary is generated mapping terms to idf values.
## Tokenizing into sentences
The default sent_tokenize from nltk library is used to split documents into a list of sentences.
## Model used
The **lexrank** algorithm has been used to find the sentence ranks. The lexrank algorithm involves finding the similarity between the sentences to calculate a similarity
matrix.The similarity is calculated using idf-modified-cosine similarity. Then the **pagerank** algorithm is applied on the similarity matrix to calculate the most prestigious page(sentence). This sentence is recommended as the title.The algorithm uses the intuition that a sentence similar to many other sentences will be more important than a sentence not similar to any other sentences.
## Title
Title is obtained by finding the sentence score to find the most important sentence, which is recommended as the title.
## How to run the file
Run the notebook till the last cell. The last cell shows the original document and title and displays the title given by the lexrank algorithm.
 

