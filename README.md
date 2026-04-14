# Adaptive Multilingual Phishing Email Detection using BERT and Generative AI

Yashita Kasina | University of Greenwich | Student ID: 001298849  
Supervisor: Dennis Ivory  


Project Overview

This project develops and evaluates an adaptive multilingual phishing email 
detection system using BERT-based natural language processing and generative 
AI techniques. The system compares a baseline BERT model trained on standard 
English data against an augmented model trained on an expanded dataset 
incorporating multilingual translations, adversarial perturbations, and 
GPT-2 generated synthetic phishing emails.

Research Question

Can multilingual and adversarial data augmentation improve the accuracy, 
robustness and cross-lingual generalisation of a BERT-based phishing 
email detection model?

Dataset

- **Source:** [drorrabin/phishing_emails-data](https://huggingface.co/datasets/drorrabin/phishing_emails-data) (Hugging Face)
- **Size:** 30,651 labelled emails
- **Labels:** safe email (0) / phishing email (1)
- **Split:** 80% training, 10% validation, 10% test
- The dataset downloads automatically when the notebook is run

Augmentation Strategy

The augmented model was trained on four types of additional data:

| Augmentation Type | Method | Samples Added |
|---|---|---|
| French Translation | Helsinki-NLP/opus-mt-en-fr | 300 |
| Spanish Translation | Helsinki-NLP/opus-mt-en-es | 300 |
| Adversarial Perturbation | WordNet synonym replacement (25% prob) | 300 |
| Synthetic Generation | GPT-2 prompt-engineered phishing emails | 300 |


 Model Architecture

- **Base model:** BERT-base-uncased (Devlin et al., 2019)
- **Classification head:** Applied to [CLS] token output
- **Task:** Binary sequence classification
- **Optimiser:** AdamW with weight decay 0.01
- **Learning rate:** 2×10⁻⁵
- **Batch size:** 16
- **Epochs:** 3
- **Max sequence length:** 256 tokens

 Results

| Metric | Baseline BERT | Augmented BERT | Improvement |
|---|---|---|---|
| Accuracy | 0.9984 | 0.9993 | +0.10% |
| Precision | 0.9986 | 1.0000 | +0.14% |
| Recall | 0.9978 | 0.9986 | +0.07% |
| F1-Score | 0.9982 | 0.9993 | +0.11% |

The augmented model outperformed the baseline across all evaluation metrics, 
demonstrating that multilingual and adversarial data augmentation improves 
phishing detection performance.

How to Run

1. Open the notebook in Google Colab
2. Set runtime to GPU: **Runtime → Change runtime type → T4 GPU**
3. Run all cells in order: **Runtime → Run all**
4. All outputs save automatically to `./outputs/`

> **Note:** The full pipeline takes approximately 2-3 hours to run.  
> Cells 4 and 9 (model training) take the longest at 30-45 minutes each.


## Repository Structure
