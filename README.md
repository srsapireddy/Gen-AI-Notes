# Gen-AI-Notes

### BERT - NER
* Text -> Tokens: Input text is tokenized.

Text -> Tokens
Input text: "John lives in New York."
Tokens (after tokenization): ['[CLS]', 'John', 'lives', 'in', 'New', 'York', '.', '[SEP]']
   
* Tokens -> Labels: Each token is assigned a label.

Tokens -> Labels
Tokens: ['[CLS]', 'John', 'lives', 'in', 'New', 'York', '.', '[SEP]']
Labels: ['O', 'B-PER', 'O', 'O', 'B-LOC', 'I-LOC', 'O', 'O']

* Labels -> Label IDs: Labels are converted to numerical IDs.

Labels -> Label IDs
Labels: ['O', 'B-PER', 'O', 'O', 'B-LOC', 'I-LOC', 'O', 'O']
Label IDs (mapping):
O → 0
B-PER → 1
I-PER → 2
B-LOC → 3
I-LOC → 4
Resulting Label IDs: [0, 1, 0, 0, 3, 4, 0, 0]

* Model Input: Tokens are processed through BERT, and corresponding label IDs are predicted.

Model Input
Tokens: ['[CLS]', 'John', 'lives', 'in', 'New', 'York', '.', '[SEP]']
Token IDs (numerical input): [101, 2198, 3268, 1999, 2047, 2259, 1012, 102]
(These are vocabulary-specific numerical representations of tokens.)
The model processes these token IDs and predicts label IDs.

* Label IDs -> Labels: Predictions are converted back to labels for evaluation.

Label IDs -> Labels
Predicted Label IDs: [0, 1, 0, 0, 3, 4, 0, 0]
Mapping back to Labels:
0 → O
1 → B-PER
3 → B-LOC
4 → I-LOC
Predicted Labels: ['O', 'B-PER', 'O', 'O', 'B-LOC', 'I-LOC', 'O', 'O']

### Final Output
From these steps:

Input Text: "John lives in New York."
NER Output: John → B-PER, New → B-LOC, York → I-LOC

This pipeline ensures that the NER system can process raw text, classify entities, and map predictions back to meaningful outputs.

