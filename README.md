GPT-2 Text Generation using the Quotes Dataset

Project Overview

This project focuses on generating human-like text using the pretrained GPT-2 model fine-tuned on a dataset of famous quotes. Text generation is an important application of Natural Language Processing because it helps in understanding how language models learn writing styles, vocabulary, and sentence structure from data.
The goal of this project was to fine-tune GPT-2 on custom quote data, generate new quote-like text from prompts, and evaluate the quality of the generated output.

Dataset : https://www.kaggle.com/datasets/manann/quotes-500k?utm_source=chatgpt.com

Project Workflow

### 1. Data Cleaning:
- Loaded and inspected the dataset
- Dropped rows with missing quotes
- Removed extra spaces and newlines from quote text 
- Sampled 3000 quotes for training

### 2. Data Preprocessing:
- Split the data into train (90%) and test (10%) sets
- Saved quotes into text files separated by GPT-2's end-of-text token
- Tokenized the text (converted words into numbers GPT-2 understands)
- Cut the token list into fixed-size chunks (block_size = 64)

### 3. Exploratory Data Analysis:
Analyzed:
- Dataset shape and column types
- Quote length distribution
- Missing value counts
- Sample quotes across different categories

### 4. Model Building:
GPT-2 was fine-tuned using the Hugging Face Trainer API:
- Base Model: gpt2 (124M parameters)
- Epochs: 3
- Batch Size: 4
- Learning Rate: 5e-5

### 6. Text Generation:
Multiple decoding methods were tested to generate text from prompts:
- Greedy Search
- Beam Search
- Top-K Sampling
- Top-P (Nucleus) Sampling

Sample Prompts and Output

| Prompt                       | Generated Text (example)                                                 |
| -----------------------------|--------------------------------------------------------------------------|
| `Once upon a time`           | Once upon a time, the only way to find peace is within yourself.         |
| `Love is`                    | Love is the bridge between two souls that never truly meet.              |
| `Life is`                    | Life is what happens when you stop waiting for it to begin.              |
| `The secret to happiness is` | The secret to happiness is learning to let go of what you cannot change. |

Decoding Method Comparison

| Method         | Characteristic                                          |
|----------------|---------------------------------------------------------|
| Greedy Search  | Picks highest probability word — fast but repetitive    |
| Beam Search    | Keeps top N sentences — more fluent, less creative      |
| Top-K Sampling | Picks randomly from top K words — more creative         |
| Top-P Sampling | Picks from words covering P% probability — most natural |


### Conclusion:

This project demonstrates how a pretrained language model like GPT-2 can be fine-tuned on a custom dataset to generate domain-specific text. By training on famous quotes, the model learns the short, meaningful, and inspirational tone of the data and can produce similar text from a given prompt.


Author : by Devaki
