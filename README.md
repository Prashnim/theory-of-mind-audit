# theory-of-mind-audit
Mini audit of small AI language models on Theory of Mind scenarios
# AI Theory of Mind: A Mini Audit with Hugging Face Models

## Overview
This is a small-scale experiment testing whether AI language models can demonstrate Theory of Mind (ToM) — the ability to reason about what others know or believe. The project uses a tiny dataset of false-belief scenarios and evaluates the model’s responses using a lightweight Hugging Face model.

## Dataset
- The dataset is embedded directly in the notebook as a Python list of scenarios; no external CSV is required.
- Each scenario tests a false-belief question,
- e.g.: "Sally puts the ball in a basket. Anne moves it while Sally is away. Where will Sally look?"  
  Correct answer: "basket"

## Model
- **Model used:** `flan-t5-small` from Hugging Face Transformers   
- Sequence-to-sequence model generates answers to the scenarios

## Workflow
1. Load the dataset (embedded in the notebook)  
2. Tokenize the scenarios using the model's tokenizer  
3. Generate answers from the model  
4. Score answers using keyword matching to handle paraphrases  
5. Visualize performance with a simple bar chart

## Results
- The AI model sometimes paraphrases answers (e.g., "Sally will look at the ball")  
- Accuracy is scored using keyword/fuzzy matching, not strict string equality  
- The notebook shows which scenarios were correct vs incorrect and the overall AI performance

## How to Run
1. Open 'AI_Theory_of_Mind.ipynb'
2. Install dependencies:  
   !pip install transformers fuzzywuzzy python-Levenshtein matplotlib pandas
3. Run all cells
