# NextWordPredictionModel

## Overview
This project aims to explore the capabilities of LSTM neural networks in natural language processing and text generation. Utilizing a dataset comprising various Sherlock Holmes stories, the model learns the patterns in word usage, sentence structure, and overall storytelling style. The outcome is a text generator that can produce new text sequences in a similar style, given a seed phrase.

## Dependencies
- Python
- Numpy
- Tensorflow
- Keras
- A dataset file (sherlock-holm.es_stories_plain-text_advs.txt) containing the text of Sherlock Holmes stories

## Data
The primary dataset is a plain text file titled sherlock-holm.es_stories_plain-text_advs.txt. This file encompasses a collection of Sherlock Holmes stories, which serve as the training material for the LSTM model. The text includes a rich variety of English vocabulary, complex sentence structures, and distinctive storytelling elements characteristic of Arthur Conan Doyle's style.

## Preprocessing
- Text Tokenization: The entire text corpus is tokenized into individual words. This process converts the text into a sequence of tokens or words.
- Sequence Creation: N-gram sequences are generated from these tokens. Each sequence is a partial phrase from the corpus, with each subsequent sequence shifting by one word.
- Padding: To ensure consistent sequence length, padding is added to the sequences.
- Data Splitting: The sequences are split into input (predictor) and output (target) datasets. The last word of each sequence is used as the output with the rest forming the input.
- One-Hot Encoding: The output data is one-hot encoded, turning it into a binary matrix essential for classification in the LSTM model.

## Model Training and Evaluation
- Model Architecture: The model comprises an Embedding layer, an LSTM layer with 150 units, and a Dense layer with a softmax activation function. The Embedding layer transforms the input sequence into dense vectors of fixed size, the LSTM layer learns the dependencies between the elements in the sequence, and the Dense layer outputs a probability distribution for the next word.
- Training: The model is compiled with a categorical cross-entropy loss function and the Adam optimizer. It is trained over 100 epochs.
- Evaluation: Model performance is evaluated based on its accuracy in predicting the next word in a sequence and its ability to generate coherent and stylistically similar text.

## Usage
- Environment Setup: Install Python 3.x and the required libraries (numpy, tensorflow, keras).
- Data Preparation: Load the sherlock-holm.es_stories_plain-text_advs.txt file and preprocess the text as described.
- Model Training: Train the LSTM model using the processed dataset.
- Text Generation: Enter a seed text and use the trained model to generate a continuation. The model predicts a fixed number of next words based on the seed text.

## Results
- The LSTM model is capable of generating new text sequences that resemble the style and context of the original Sherlock Holmes stories.
- The quality of generated text varies, showcasing both the model's understanding of language patterns and the inherent challenges in deep learning-based text generation.
