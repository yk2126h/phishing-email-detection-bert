PHISHING EMAIL DETECTION - BERT BASED CLASSIFICATION
Author: Yashita Kasina | University of Greenwich | Student ID: 001298849
Supervisor: Dennis Ivory
Module: COMP1682 Final Year Project

GitHub Repository:
https://github.com/yk2126h/phishing-email-detection-bert

HOW TO RUN: 
1. Open Phishing_Detector_Submission.ipynb in Google Colab
2. Set runtime to GPU: Runtime > Change runtime type > T4 GPU
3. Run all cells in order: Runtime > Run all
4. All outputs save automatically to ./outputs/

REQUIREMENTS:

transformers
datasets
torch
scikit-learn
pandas
matplotlib
seaborn
tqdm
nltk

All packages are pre-installed in Google Colab.
No API keys required. No Google Drive connection required.
Dataset downloads automatically from Hugging Face.

ESTIMATED RUNTIME:

Full pipeline: approximately 2-3 hours
Cell 4 (baseline training): 30-45 minutes
Cell 8 (GPT-2 generation): 10-15 minutes
Cell 9 (augmented training): 30-45 minutes

OUTPUT FILES:

./outputs/baseline_confusion_matrix.png
./outputs/baseline_training_curves.png
./outputs/fr_translations.csv
./outputs/es_translations.csv
./outputs/adv_samples.csv
./outputs/gpt_samples.csv
./outputs/final_comparison_graph.png
./outputs/final_confusion_matrices.png
./outputs/final_results_comparison.csv