# BERT-Transformer
Training A BERT model from scratch.

## Project Goal
- The goal of the project is to train a BERT- model from scratch, Bidirectional Encoder Representations from Transformers (BERT) is a transformer-based machine learning technique for natural language processing (NLP) pre-training developed by Google. BERT was created and published in 2018 by Jacob Devlin and his colleagues from Google.

## Overview
There are a few steps to the process, so before we dive in let’s first summarize what we need to do. In total, there are four key parts:
- Getting the data
- Building a tokenizer
- Creating an input pipeline
- Training the model

- After we have worked through each of the sections, we will take the tokenizer and the model we have built and save them both so that we can then use them in the same way we usually would with from_pretrained.

## Getting The Data
- As with any machine learning project, we need data. In terms of data for training a transformer model, we will use a Shakespeare Sonnet as the training data.

## Building a tokenizer
- We’ll start with a single sample and work through the preparation logic.
- First, we will open the training data file — the same file that we saved as .txt files earlier. We split each based on newline characters \n as this indicates the individual samples.
- Next we will make a tokenizer, when using transformers we typically load a tokenizer, alongside its respective transformer model — the tokenizer is a key component in the process.
## Creating an input pipeline
- For the input pipeline we will move onto creating our tensors — we will be training our model through masked-language modeling (MLM). So, we need three tensors:
- input_ids — our token_ids with ~15% of tokens masked using the mask token <mask.
- attention_mask — a tensor of 1s and 0s, marking the position of ‘real’ tokens/padding tokens — used in attention calculations.
- labels — our token_ids with no masking.
- Our attention_mask and labels tensors are simply extracted from our batch. 

The input_ids tensors require more attention however, for this tensor we mask ~15% of the tokens — assigning them the token ID 3.

## Training the model
- We need two things for training, our DataLoader and a model. The DataLoader we have — but no model.
Initializing the Model:
-  For training, we need a raw (not pre-trained) BERTLMHeadModel. To create that, we first need to create a RoBERTa config object to describe the parameters we’d like to initialize FiliBERTo with.
- Then, we import and initialize our RoBERTa model with a language modeling (LM) head.
Training Preparation:
- Before moving onto our training loop we need to set up a few things. First, we set up GPU/CPU usage. Then we activate the training mode of our model — and finally, initialize our optimizer.
Training, after this we will train the PYtorch model.

## Testing the Model
- After that we will test the model to check the output given by our model.

