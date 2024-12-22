# Gen-AI-Notes

### [1] BERT - NER
* Text -> Tokens: Input text is tokenized.

Text -> Tokens </br>
Input text: "John lives in New York."</br>
Tokens (after tokenization): ['[CLS]', 'John', 'lives', 'in', 'New', 'York', '.', '[SEP]']</br>
   
* Tokens -> Labels: Each token is assigned a label.

Tokens -> Labels</br>
Tokens: ['[CLS]', 'John', 'lives', 'in', 'New', 'York', '.', '[SEP]']</br>
Labels: ['O', 'B-PER', 'O', 'O', 'B-LOC', 'I-LOC', 'O', 'O']</br>

* Labels -> Label IDs: Labels are converted to numerical IDs.

Labels -> Label IDs</br>
Labels: ['O', 'B-PER', 'O', 'O', 'B-LOC', 'I-LOC', 'O', 'O']</br>
Label IDs (mapping):</br>
O → 0</br>
B-PER → 1</br>
I-PER → 2</br>
B-LOC → 3</br>
I-LOC → 4</br>
Resulting Label IDs: [0, 1, 0, 0, 3, 4, 0, 0]

* Model Input: Tokens are processed through BERT, and corresponding label IDs are predicted.

Model Input</br>
Tokens: ['[CLS]', 'John', 'lives', 'in', 'New', 'York', '.', '[SEP]']</br>
Token IDs (numerical input): [101, 2198, 3268, 1999, 2047, 2259, 1012, 102]</br>
(These are vocabulary-specific numerical representations of tokens.)</br>
The model processes these token IDs and predicts label IDs.</br>

* Label IDs -> Labels: Predictions are converted back to labels for evaluation.

Label IDs -> Labels</br>
Predicted Label IDs: [0, 1, 0, 0, 3, 4, 0, 0]</br>
Mapping back to Labels:</br>
0 → O</br>
1 → B-PER</br>
3 → B-LOC</br>
4 → I-LOC</br>
Predicted Labels: ['O', 'B-PER', 'O', 'O', 'B-LOC', 'I-LOC', 'O', 'O']

### Final Output
From these steps:</br>

Input Text: "John lives in New York."</br>
NER Output: John → B-PER, New → B-LOC, York → I-LOC</br>

This pipeline ensures that the NER system can process raw text, classify entities, and map predictions back to meaningful outputs.

### [2] HUGGINGFACE TEXT SUMMARIZER
* https://huggingface.co/docs/transformers/en/tasks/summarization
* https://huggingface.co/google/pegasus-large
* https://huggingface.co/google/pegasus-cnn_dailymail
* Seq2seq model
  ![image](https://github.com/user-attachments/assets/73cf5d8a-c116-4ecb-8439-665cbfbe7686)
* https://huggingface.co/docs/datasets/en/upload_dataset

