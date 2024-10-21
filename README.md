# Next_word predictor

# Data Science Mentorship Program (DSMP 2023) FAQ Processing

This project uses TensorFlow's `Tokenizer` from the `tensorflow.keras.preprocessing.text` module to tokenize and process the FAQs of the **Data Science Mentorship Program (DSMP 2023)**.

## Table of Contents
- [Project Description](#project-description)
- [FAQ Dataset](#faq-dataset)
- [Technologies Used](#technologies-used)
- [How to Run the Project](#how-to-run-the-project)
- [Usage](#usage)
- [FAQ List](#faq-list)
- [Contributing](#contributing)
- [License](#license)

## Project Description

This project tokenizes the frequently asked questions (FAQs) provided for the **DSMP 2023**. It aims to process the FAQ content using NLP techniques, specifically tokenization. Tokenization is the first step toward preparing text data for machine learning models, and this project provides a simple and straightforward approach to that task.

The key objective of the project is to:
- Tokenize the FAQ dataset.
- Prepare input sequences from the tokenized data for further NLP tasks.

## FAQ Dataset

The FAQ dataset covers the following topics about the Data Science Mentorship Program:
- Course fee and payment details.
- Course duration and syllabus.
- Class schedules and live session information.
- Subscription model and validity.
- Refund policies.
- Post-registration and doubt clearing process.
- Certification and placement assistance criteria.

## Technologies Used

- **Python**: The programming language used for implementing the tokenizer.
- **TensorFlow**: The deep learning framework used for tokenizing and processing the text data.
- **Keras Tokenizer**: To split the text into tokens for NLP processing.

## How to Run the Project

### Prerequisites
- Python 3.x
- TensorFlow 2.x

### Installation
1. Clone this repository:
    ```bash
    git clone (https://github.com/akhileshkrsingh1/Next_word_predictor)
    cd dsmp-faq-tokenizer
    ```

2. Install required dependencies:
    ```bash
    pip install tensorflow
    ```

### Run the Code
1. Run the Python script to tokenize the FAQ data:
    ```bash
    python tokenizer_script.py
    ```

This will generate tokenized sequences from the FAQ text data.

## Usage

The project demonstrates how to:
- Use TensorFlow's `Tokenizer` to convert text data into a sequence of tokens.
- Generate input sequences for NLP tasks.

### Example
The following code snippet shows how the tokenizer is used:
```python
import tensorflow as tf
from tensorflow.keras.preprocessing.text import Tokenizer

faqs = """..."""  # FAQ dataset (see full content in the project)

tokenizer = Tokenizer()
tokenizer.fit_on_texts([faqs])

input_sequences = []
for sentence in faqs.split('\n'):
  tokenized_sentence = tokenizer.texts_to_sequences([sentence])[0]
  for i in range(1, len(tokenized_sentence)):
    input_sequences.append(tokenized_sentence[:i+1])

