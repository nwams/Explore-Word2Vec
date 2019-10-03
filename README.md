# Word2Vec-Visualize-Implement
Here I explore two types of word vectors: those derived from co-occurrence matrices, and those derived via word2vec.

# Word Vectors
Word Vectors are often used as a fundamental component for downstream NLP tasks, e.g. question answering, text generation, translation, etc., so it is important to build some intuitions as to their strengths and weaknesses. Here, you will explore two types of word vectors: those derived from co-occurrence matrices, and those derived via word2vec.

**Note on Terminology**: The terms "word vectors" and "word embeddings" are often used interchangeably. The term "embedding" refers to the fact that we are encoding aspects of a word's meaning in a lower dimensional space. As Wikipedia states, "conceptually it involves a mathematical embedding from a space with one dimension per word to a continuous vector space with a much lower dimension".

## Part 1: Count-Based Word vectors
Many word vector implementations are driven by the idea that similar words, i.e., (near) synonyms, will be used in similar contexts. As a result, similar words will often be spoken or written along with a shared subset of words, i.e., contexts. By examining these contexts, we can try to develop embeddings for our words.
* **Create a Co-occurrences Matrix**:  I create a co-occurrence matrix. A co-occurrence matrix counts how often things co-occur in some environment.
* **Dimensionality reduction**: Use [`sklearn.decomposition.TruncatedSVD`](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.TruncatedSVD.html) and construct a method that performs dimensionality reduction on the matrix to produce k-dimensional embeddings. Use SVD to take the top _k_ components and produce a new matrix of k-dimensional embeddings.

## Part 2: Prediction-Based Word Vectors
Here I explore the embeddings produced by word2vec. Please revisit the class notes and lecture slides for more details on the word2vec algorithm
* **Reduce dimensionality** of Word2Vec Word Embeddings
* **Synonyms & Antonyms**: Demonstrate counter-intuitive examples and explore why they happen.
* **Solving Analogies with Word Vectors**: I use gensim to solve analogies. For example, for the analogy "man : king :: woman : x", what is x?
* **Finding Analogies**: Use [GenSim's](https://radimrehurek.com/gensim/models/keyedvectors.html#gensim.models.keyedvectors.FastTextKeyedVectors.most_similar) `most_similar` function to find analogies, e.g. Austin is the capital of Texas, and Atlanta is the capital of Georgia.
* **Explore Incorrect Analogies**: Gensim doesn't always produce correct results. Here I explore that.
* **Analyze bias in Word Vectors**: Use the `most_similar` function to find another case where some bias is exhibited by the vectors. E.g. I discovered that there's a bias which results in the correlation of mothers and doctors to nurse. While father and doctors is correlated to physician.
