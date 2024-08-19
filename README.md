# Spacy POS-Tagging and Dependency Parsing

This project demonstrates the use of the spaCy library to perform Part-Of-Speech (POS) tagging, dependency parsing, and visualization of a given sentence. The goal is to extract nouns, adjectives, and grammatical relationships between words, and to visualize the dependency tree.

## Project Overview

### Objectives

1. **POS Tagging**:
   - Tokenize the sentence and identify the Part-Of-Speech (POS) tags for each token.
   - Extract and display specific POS tags, such as nouns and adjectives.

2. **Dependency Parsing**:
   - Analyze the grammatical relationships between words in the sentence.
   - Visualize the dependency tree using spaCy’s `displacy` tool.

3. **Customization**:
   - Customize the appearance of the dependency tree with colors and styles for better readability.

## Tools and Libraries

- **spaCy**: A powerful NLP library in Python used for POS tagging, dependency parsing, and visualization.
- **displacy**: A visualization tool from spaCy to render dependency trees.

## Key Steps and Functions

### 1. POS Tagging

- **Loading the Model**:
  - Load the small English language model (`en_core_web_sm`) provided by spaCy.
  - Example:
    ```python
    nlp = spacy.load("en_core_web_sm")
    ```

- **Tokenization and POS Tagging**:
  - Tokenize a given sentence and analyze each token to identify its POS tag.
  - Example Sentence: "The brown cow jumped over the round moon."
  - Example POS Tags:
    ```python
    ['The ---> DET', 'brown ---> ADJ', 'cow ---> NOUN', 'jumped ---> VERB', 
     'over ---> ADP', 'the ---> DET', 'round ---> ADJ', 'moon ---> NOUN', '. ---> PUNCT']
    ```

- **Extracting Nouns**:
  - Retrieve all the nouns from the sentence using a list comprehension.
  - Example Output:
    ```python
    ['cow', 'moon']
    ```

### 2. Dependency Parsing

- **Grammatical Dependencies**:
  - Analyze and print the grammatical dependencies for each token in the sentence.
  - Example Output:
    ```python
    ['The ---> det', 'brown ---> amod', 'cow ---> nsubj', 
     'jumped ---> ROOT', 'over ---> prep', 'the ---> det', 
     'round ---> amod', 'moon ---> pobj', '. ---> punct']
    ```

- **Dependency Visualization**:
  - Visualize the dependency tree using spaCy’s `displacy` tool.
  - Example Visualization:
    - A tree showing the syntactic structure of the sentence with labels like `nsubj` (nominal subject) and `ROOT`.

- **Customization**:
  - Customize the appearance of the dependency tree with options such as `color`, `bg` (background color), and `font`.
  - Example Customization:
    ```python
    options = {'distance': 125, 'compact': 'True', 'color': 'yellow', 
               'bg': 'navy', 'font': 'Arial'}
    ```

### 3. Specific Adjective Extraction

- **Describing Nouns**:
  - Extract adjectives that describe a specific noun (e.g., "cow") using a list comprehension.
  - Example Output:
    ```python
    ['brown']
    ```

## Results

### POS Tags and Grammatical Dependencies

- The sentence was successfully tokenized, and POS tags were assigned to each token.
- The grammatical relationships between words were identified and visualized, providing insights into the sentence structure.

### Visualization

- The dependency tree was rendered using `displacy`, with custom styles applied for better readability.

### Noun and Adjective Extraction

- The nouns "cow" and "moon" were identified from the sentence.
- The adjective "brown" was correctly associated with the noun "cow".

## Requirements

- Python 3.x
- spaCy

## Installation

To install the required library, use the following pip command:

```bash
pip install spacy
python -m spacy download en_core_web_sm
```

## How to Run

1. Ensure the required library is installed.
2. Load the spaCy model using `nlp = spacy.load("en_core_web_sm")`.
3. Run the script to analyze the given sentence. The output will include POS tags, grammatical dependencies, extracted nouns, and adjectives, as well as a visualization of the dependency tree.

## Conclusion

This project demonstrates the application of spaCy for natural language processing tasks, such as POS tagging and dependency parsing. The visualization of the dependency tree provides a clear understanding of the grammatical structure of a sentence, while the extraction of specific POS tags and descriptors adds to the analysis.
