# Notes on Embedding (Unit 2)

## Table of Contents

1. [Introduction - Key task of embeddings](#introduction-key-task-of-embeddings)
2. [Why embeddings?](#why-embeddings)
3. [Steps from input to embedding](#steps-from-input-to-embedding)
4. [Embedding quality](#embedding-quality)
5. [Embedding types](#embedding-types)

## Introduction - Key task of embeddings

- Turning all kind of data (heterogeneous data) into a vector representation (embedding) that can be used for downstream tasks
- Advantage: Embeddings are low-dimensional and dense representations of data but still preserve the semantic meaning of the data

## Why embeddings?

- Embeddings are expressed as low-dimensional vectors
- The geometric distance between two vectors is a measure of their semantic similarity
- The closer the vectors are, the more similar the data is
- Helps with large-scale data processing and storage
- Concrete embedding depends on the type of data and the task at hand
- Key applications: retrieval (like searching for information) and recommendation

### Special case of joint embedding

- Joint embedding &rarr; embedding of two different modalities (e.g., text and image) into the same vector space

## Steps from input to embedding

1. Input text
    - Example: "The cat sat on the mat."
2. Tokenization: Split the text into tokens (words or subwords)
    - Example: ["The", "cat", "sat", "on", "the", "mat"]
3. Indexing: Map each token to a unique index in the vocabulary
    - Example: [1, 2, 3, 4, 5, 6]
4. Embedding: Convert each token index into a dense vector representation (embedding)

## Embedding quality

- For search cases: precision and recall
    - precision: all documents retrieved should be relevant
    - recall: all relevant documents should be retrieved
- Drawback of precision and recall: All documents are treated equally
    - Some documents are more relevant than others
- Metric for taking relevancy into account: Normalized Discounted Cumulative Gain (nDCG)
    - DCG: measures the gain of a document based on its position in the ranked list of documents
    - nDCG: normalizes DCG to a value between 0 and 1

## Embedding types

### Text embedding

#### Word embedding

- Focus on representing individual words as vectors
- Techniques: Word2Vec, GloVe, SWIVEL
- **Word2Vev**:
    - Retrieves semantic meaning of words based on the neighbors
    - Two architectures: **Continuous Bag of Words (CBOW)** and **Skip-gram**
    - CBOW: Predicts the target word based on the context words
    - Skip-gram: Predicts the context words based on the target word
    - Disadvantage: Does not capture the global context of the word (e.g. document-level)
- **GloVe**:
    - Tries to capture the global level as well
    - Uses the co-occurrence matrix of words in a corpus to model the relationships between words
- **SWIVEL** (Skip-Window Vectors with Negative Sampling):
    - Uses co-occurrence matrix as well
    - Also considers unobserved co-occurrences (negative sampling)
    - Is faster than GloVe

#### Document embedding

- Aim: Represent entire documents as vectors

##### Bag-of-Words (BoW) approaches
- Early approaches: **Bag-of-Words (BoW)**
- **BoW** includes approaches like:
    - Latent Semantic Analysis (LSA)
    - Latent Dirichlet Allocation (LDA) using a bayesian network to model document embeddings
    - TF-IDF (Term Frequency-Inverse Document Frequency) using word frequency to model document embeddings
- **Weaknesses**
    - Does not capture the order of words in the document
    - Does not capture the semantic meaning of the words

##### More recent approaches: Deeper pretrained LLMs

### Image and multimodal embedding

- Unimodal image embedding: Represent images as vectors using Convolutional Neural Networks (CNNs)
- Multimodal embedding: Jointly represent text and image data in the same vector space

### Structured data embedding

- Created for specific applications
- General structured data &rarr; use methods like PCA to create embeddings for each row in the table
- User/ item structured data &rarr; for recommendation

### Graph embedding

- Aim: Capture objects and their relationships &rarr; capture individual points but also their connections and associations