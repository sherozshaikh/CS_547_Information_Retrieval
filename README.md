# 🎓 University & Course Details
- **Course**: CS 547 - Information Retrieval
- **University**: Worcester Polytechnic Institute
- **Semester**: Fall 2023

# 🌍 Cross-Lingual Information Retrieval

## 👨‍💻 Authors
- [Shaun Noronha](https://github.com/Shaun-Noronha)
- [Sheroz Shaikh](https://github.com/sherozshaikh)

## 🌟 Background and Motivation
Our cross-lingual information retrieval tool is designed to extract relevant documents from a large corpus based on user-specified queries in any of seven languages: Arabic (Ar), Bengali (Bn), Finnish (Fi), Japanese (Ja), Korean (Ko), Russian (Ru), and Telugu (Te). Unlike traditional methods that rely on machine translation, our tool can retrieve the most relevant top-k documents without the need for translation, which can sometimes introduce errors or hinder retrieval performance. By directly accessing relevant documents in their original language, users can enjoy a seamless and efficient information retrieval experience, avoiding potential issues with translation quality or ambiguity.

## 📚 Dataset
### Cross-lingual Open-Retrieval Question Answering Data
We used the data available on [XOR-TyDi](https://nlp.cs.washington.edu/xorqa/), which provides a rich source of cross-lingual question-and-answer data. This dataset offers a comprehensive view of queries, correct and incorrect answers, and allows for a realistic assessment of our information retrieval tool.

<p align="middle">
  <img src="Table-1.jpg" width="450" />
</p>

### Dataset Columns

| Column |Description|
|-------|--------|
| Query | Queries in various languages |
| Correct Answers /Document | Correct answers for the documents |
| Incorrect Answers /Document | Incorrect answers for the documents |

## 🔎 Exploratory Data Analysis

Among the datasets assessed for this project, this dataset was chosen for its unique inclusion of random instances and nuanced complexities. It provides a diverse range of data patterns that mirror real-world scenarios, allowing our model to learn from varied examples, and ensuring adaptability to unforeseen circumstances. The ultimate goal is to equip the model with the robustness required for practical applications, improving its performance in real-world deployments.

## 🛠️ Implementation

Our implementation involves training and testing data for model evaluation:
- **Training Data**: 80% of the dataset is used for training.
- **Test Data**: 20% is reserved for testing and validation.
For the demonstration, we use less than 1% of the data to ensure quick inference.

### Bi-directional LSTM

Bidirectional Long Short-Term Memory (BiLSTM) is a powerful recurrent neural network used in our project for its capability to process information from both directions. It captures sequential dependencies, allowing a more profound understanding of textual context.

<p align="middle">
  <img src="bilstm-1.jpg" width="450" /> 
</p>


### Nearest-Neighbours Approach

The nearest-neighbors model is used for identifying similar items or data points based on their proximity in a feature space. This technique is crucial for information retrieval, as it helps find the most relevant documents based on user queries.

### Approximate Nearest Neighbor (Annoy)

Annoy is a library designed for high-dimensional data, allowing fast and approximate nearest-neighbor searches. It's beneficial for handling large datasets and is widely used in recommendation systems, information retrieval, clustering, and other machine-learning applications.

### HNSW (Hierarchical Navigable Small World) Library

HNSW provides efficient approximate nearest-neighbor searches by constructing a hierarchical graph structure. This method allows for quick searches and maintains global and local connectivity, making it a robust solution for high-dimensional data.

#### Model Design

Here's the model used in our implementation:

The model used is seen below:
<p align="middle">
  <img src="LSTM.jpg" width="250" />
</p>

## ✨ Conclusion & Future Work

1. The performance of different nearest-neighbor search methods (NearestNeighbors, AnnoyIndex, HNSWLib) can vary. Comparing their accuracy, efficiency, and recall rates is essential to identify the best approach.

|    |   Index_IDS |   NearestNeighbors |   AnnoyIndex |   HNSWLib |   Best_Of_3 |   Neighbours |
|----|-------------|--------------------|--------------|-----------|-------------|--------------|
|  0 |          44 |                  1 |            1 |         1 |           1 |            2 |      
|  1 |          44 |                  1 |            1 |         1 |           1 |            5 |     
|  2 |          44 |                  1 |            1 |         1 |           1 |           10 |     
|  3 |        1156 |                  1 |            1 |         1 |           1 |            2 |     
|  4 |        1156 |                  1 |            1 |         1 |           1 |            5 |     
|  5 |        1156 |                  1 |            1 |         1 |           1 |           10 |     
|  6 |        2132 |                  1 |            1 |         1 |           1 |            2 |     
|  7 |        2132 |                  1 |            1 |         1 |           1 |            5 |     
|  8 |        2132 |                  1 |            1 |         1 |           1 |           10 |     
|  9 |        9982 |                  1 |            1 |         1 |           1 |            2 |     
| 10 |        9982 |                  1 |            1 |         1 |           1 |            5 |     
| 11 |        9982 |                  1 |            1 |         1 |           1 |           10 |     
| 12 |        9995 |                  1 |            1 |         1 |           1 |            2 |     

2. Using a sentence tokenizer from the BERT family offers significant advantages. It can improve text tokenization and facilitate better embeddings for natural language processing.

3. Employing exact nearest-neighbor search metrics like cosine similarity or Euclidean distance can improve the accuracy and refinement of the search process.

## 🏛️ GitHub Repository
For the complete project, you can visit our GitHub repository [here](https://github.com/sherozshaikh/CS_547_Information_Retrieval).

## 📚 References
The following references provided inspiration and guidance for this project:

1. Shengyao Z., Linjun S., Guido Z. (2023). "Augmenting Passage Representations with Query Generation for Enhanced Cross-Lingual Dense Retrieval." SIGIR (2023). [Link](https://doi.org/10.48550/arXiv.2305.03950)
2. Zhuolin J., El-Jaroudi A., William H., Damianos K., Lingjun Z. (2020). "Cross-lingual Information Retrieval with BERT." [Link](https://doi.org/10.48550/arXiv.2004.13005)
3. Yulong Li, Martin Franz, Md Arafat Sultan, Bhavani Iyer, Young-Suk Lee, Avirup Sil (2022). "Learning Cross-Lingual IR from an English Retriever." NAACL (2022). [Link](https://doi.org/10.48550/arXiv.2112.08185)
