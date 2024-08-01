# Urdu to English Machine Translation (Fine-tuning transformer)

This project demonstrates a machine translation system that translates Urdu text into English using the Hugging Face `transformers` library.

## Table of Contents
- [Setup](#setup)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Model Training](#model-training)
- [Evaluation](#evaluation)
- [Usage](#usage)
- [Results](#results)

## Setup

To get started, install the necessary dependencies:

```bash
pip install datasets
pip install transformers
pip install sacrebleu
pip install evaluate
pip install accelerate -U
```

## Dataset

The dataset used for this project consists of Urdu to English sentence pairs. Ensure your dataset is structured with each pair on a new line, separated by a tab.

## Preprocessing

1. **Load the dataset**:
    - Read the dataset from a file.
    - Split the dataset into training, validation, and testing sets.

2. **Convert to Hugging Face `Dataset` format**:
    - Convert the data to dictionaries.
    - Create `DatasetDict` with training, validation, and testing sets.

3. **Tokenization**:
    - Tokenize the sentences using the `Helsinki-NLP/opus-mt-ur-en` tokenizer.

## Model Training

1. **Define Model**:
    - Load the pre-trained model and tokenizer from Hugging Face.

2. **Freeze Specific Layers**:
    - Freeze the initial layers of the encoder and decoder to focus training on the remaining layers.

3. **Training Arguments**:
    - Set training arguments such as learning rate, batch size, evaluation steps, etc.

4. **Train**:
    - Use the `Seq2SeqTrainer` to train the model.

## Evaluation

1. **Metric**:
    - Use BLEU score for evaluation with the `evaluate` library.

2. **Evaluate**:
    - Evaluate the model on the test dataset.

## Usage

1. **Load the Model**:
    - Load the fine-tuned model and tokenizer.

2. **Translate Text**:
    - Encode the Urdu text and generate the English translation.

## Results

After training, evaluate the model to check its performance on the test dataset. The evaluation results will include BLEU scores and other relevant metrics.
