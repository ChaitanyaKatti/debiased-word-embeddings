# Word Embeddings Analysis and Hard Debiasing

![1_SYiW1MUZul1NvL1kc1RxwQ](https://github.com/ChaitanyaKatti/debiased-word-embeddings/assets/96473570/d77ddc7a-7ea8-41c2-b1d3-3bd3f65b58f6)


Welcome to my GitHub repository! This project focuses on the analysis of various word embeddings on word analogy tasks and showcases the implementation of the Hard Debiasing technique to mitigate gender bias. Word embeddings play a vital role in Natural Language Processing (NLP) tasks, enabling us to represent words in a dense vector space, capturing their semantic relationships.

## Table of Contents

1. [Introduction](#iIntroduction)
2. [Word Analogy Tasks](#word-analogy-tasks)
3. [Word Embeddings](#word-embeddings)
4. [Evaluation](#evaluation)
5. [Hard Debiasing](#hard-debiasing)
6. [Results](#results)
7. [How to Use](#how-to-use)
8. [License](#license)

## Introduction

Word embeddings have revolutionized NLP tasks by converting words into numerical representations. These embeddings capture semantic and syntactic relationships betIen words, allowing us to perform analogical reasoning, such as "king - man + woman = queen." This project aims to analyze various word embeddings using word analogy tasks and apply Hard Debiasing to mitigate any gender bias present in the embeddings.

## Word Analogy Tasks

To assess the quality of word embeddings, I employ word analogy tasks. These tasks typically take the form of word analogies like "a is to b as c is to __." By understanding the relationships betIen words, I can predict the missing word. We have curated a set of diverse analogy tasks to evaluate the performance of word embeddings. We will be using the google analogy dataset.

Link `https://aclweb.org/aclwiki/Google_analogy_test_set_(State_of_the_art)`

## Word Embeddings

The repository includes pre-trained word embeddings using popular algorithms like Word2Vec, GloVe, and FastText. Each embedding captures different linguistic patterns and contexts. We provide detailed information about the embeddings, including their dimensions, vocabulary size, and training corpora sources.
The embeddings are trained on the IMDB movie reviews dataset

Link:`https://ai.stanford.edu/~amaas/data/sentiment/`

## Evaluation

We have developed an evaluation pipeline to test the word embeddings on the analogy tasks. The results are compared based on accuracy and speed of inference. Additionally, I visualize the embeddings using t-SNE and other dimensionality reduction techniques to gain insights into their clustering behavior.

![image](https://github.com/ChaitanyaKatti/debiased-word-embeddings/assets/96473570/7e397857-a604-4480-acf7-fcc0f29af57c)


## Hard Debiasing

One significant concern with word embeddings is the potential presence of gender bias, which can be reflected in analogies or downstream NLP tasks. We address this issue by implementing the Hard Debiasing technique. This method aims to neutralize gender-specific information from the embeddings without significantly altering their semantic properties.


### Gender Bias in Word Embeddings
Word embeddings are learned from large corpora of text data, which might contain societal biases, including gender bias. For example, certain professions might be associated more with one gender, leading to biased word representations.

### Neutralizing Gender Bias
The Hard Debiasing technique aims to neutralize gender-specific information in word embeddings. It involves two main steps:

1. Identify Gender Direction: The first step is to determine the gender direction in the word embeddings. This direction is calculated as the vector obtained by subtracting the embedding of a gender-defining word (e.g., "he") from the embedding of its counterpart (e.g., "she"). This gender direction represents the bias present in the embeddings.

2. Neutralize Gender Bias: In this step, the embeddings of gender-specific words (e.g., "he" and "she") are projected onto the hyperplane perpendicular to the gender direction. By doing this, the gender information is removed from these specific words, effectively neutralizing the gender bias in the embeddings.

### Preserving Semantic Information
It is important to note that the Hard Debiasing technique aims to neutralize gender bias while preserving the semantic information captured by the embeddings. It ensures that the relationships betIen words and the overall structure of the embedding space remain intact.

### Implementation
In this repository, I have included an implementation of the Hard Debiasing technique. You can find the debiasing script in the hard_debias.py file. By running this script on your word embeddings, you can mitigate gender bias and make your embeddings more inclusive.

To use the Hard Debiasing implementation, follow the steps in the How to Use section of this README.

The Hard Debiasing technique is an effective approach to address gender bias in word embeddings, making them more suitable for various NLP applications and promoting fairness in AI systems.

For more details on the Hard Debiasing technique and its effectiveness, please refer to the original research paper: Hard Debiasing Word Embeddings and Fairness in Word Analogy Tasks.
## Results

my analysis provides an in-depth comparison of different word embeddings on word analogy tasks. We also demonstrate the effectiveness of the Hard Debiasing technique in reducing gender bias in the embeddings. The results are presented in a clear and visually appealing manner through tables and plots.


## How to Use

To get started with this project, follow these steps:

1. Clone the repository: `git clone https://github.com/ChaitanyaKatti/debiased-word-embeddings.git`
2. Install the required dependencies: `pip install -r requirements.txt`
3. Explore the word embeddings and their properties in the `data` directory.
4. Run the word analogy evaluation script: `python movie_data_project.ipynb`

## License

This project is licensed under the [MIT License](LICENSE), allowing you to use, modify, and distribute the code freely.

Let's make NLP more inclusive and bias-free together!

**Happy coding!** :rocket:
