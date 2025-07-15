# Text-Summarization With transformer models

# Abstractive Text Summarization with Transformer Models  
This project explores the effectiveness of transformer-based models like T5 and PEGASUS, BERT for abstractive text summarization, comparing them with traditional NLP methods. The model is trained on the WikiHow dataset and evaluated using standard summarization metrics.  
  
## Project Objectives  
Fine-tune pre-trained transformer models (T5, BERT, PEGASUS).  
Compare transformer-based summarization with traditional extractive methods.  
Evaluate models using ROUGE and BLEU metrics.  
Analyze training progression over epochs.  
Perform side-by-side inference comparisons using T5 and PEGASUS.  
  
## Project Structure  
Text-Summarization-Transformers  
 
├── scripts/  
│   ├── training_script.py  
│   ├── inference_epoch1_5.py  
│   └── inference_vs_pegasus.py  

  
## Dataset  
- **WikiHowAll.csv**  
  Used `text` as input and `headline` as the summary.  
  Preprocessing: column filtering, tokenization (512 for text, 128 for headline), saved as `.pt` files.  
  
##  Models Used  
- T5-small: Fine-tuned on WikiHow dataset for summarization.  
- PEGASUS: Used for pre-trained inference-based comparison.  
- BERT: Initially explored but not used due to slower performance and less relevance to abstractive tasks.  
  
## Code Overview  
  
🔹 [training_script.py]  
- Loads tokenized training and validation datasets.  
- Fine-tunes `T5ForConditionalGeneration`.  
- Uses PyTorch with Hugging Face Transformers.  
- Saves a checkpoint after each epoch.  
  
🔹 [inference_epoch1_5.py]  
- Loads T5 models from Epoch 1 and Epoch 5.  
- Generates summaries for the same input to track performance improvements.  
  
🔹 [inference_vs_pegasus.py]  
- Loads T5 (Epoch 5) and pre-trained PEGASUS models.  
- Generates summaries from both for comparison.  
- Helps in qualitative model evaluation.  
  
##  Evaluation 

The T5 achieved best results among three.
  
| Model      | ROUGE-1 | ROUGE-2 | ROUGE-L | BLEU  |  
|------------|---------|---------|---------|-------|  
| T5 (ours)  | 31.34   | 11.72   | 26.08   | 10.96 |  
  
  
  

