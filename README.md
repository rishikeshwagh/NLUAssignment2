# Sanskrit-to-English Neural Machine Translation using Seq2Seq with Attention

## Overview

This repository contains the implementation of **Assignment 2** for the **Natural Language Understanding** course. The objective of this project is to develop a custom **Sequence-to-Sequence (Seq2Seq) Neural Machine Translation (NMT)** model with an **Attention Mechanism** to translate Sanskrit sentences into English.

The model is implemented using **PyTorch** and trained on the provided Sanskrit-English parallel corpus. Model performance is evaluated using **BLEU Score**, **Rescaled BERTScore (F1)**, inference time, and model parameter count.

---

## Repository Structure

```
.
├── NLUAssignment2.ipynb          # Complete implementation
├── submission.csv                # Final test predictions
├── G25AIT1138_NLU_Report.pdf     # Project report
├── README.md                     # Project documentation
└── requirements.txt              # Python dependencies (recommended)
```

---

## Dataset

The project uses the Sanskrit-English parallel dataset provided as part of the assignment.

| Dataset | Samples |
|----------|--------:|
| Training | 10,000 |
| Development | 1,000 |
| Test | 1,000 |

Each Sanskrit sentence is paired with its corresponding English translation using a common **Source ID**.

---

## Model Architecture

The proposed Neural Machine Translation system consists of:

- Encoder Network
- Decoder Network
- Attention Mechanism
- Greedy Decoding

Beam Search was **not implemented** in the current version.

---

## Preprocessing

The preprocessing pipeline includes:

- Text tokenization
- Vocabulary generation
- Special tokens (SOS, EOS, PAD, UNK)
- Sequence padding
- Mini-batch preparation

---

## Training Configuration

| Parameter | Value |
|-----------|-------|
| Epochs | 10 |
| Optimizer | Adam |
| Loss Function | Cross Entropy Loss |
| Decoder Strategy | Greedy Decoding |
| Beam Search | Not Implemented |
| Trainable Parameters | 17,270,240 |

---

## Evaluation Results

| Metric | Value |
|---------|------:|
| BLEU Score | **0.0077** |
| Rescaled BERTScore (F1) | **0.0679** |
| Total Trainable Parameters | **17,270,240** |
| Test Inference Time | **4.00 seconds** |

---

## Training Analysis

The training loss decreased steadily throughout training, indicating successful optimization on the training dataset. However, the validation loss gradually increased after the initial epochs, suggesting overfitting. Consequently, the model achieved relatively low BLEU and BERTScore values despite successful convergence.

---

## Requirements

Install the required Python packages using:

```bash
pip install -r requirements.txt
```

or install manually:

```bash
pip install torch torchvision torchaudio
pip install pandas numpy matplotlib nltk
pip install bert-score
pip install sentencepiece
pip install tqdm
```

---

## Running the Project

1. Clone the repository.

```bash
git clone https://github.com/rishikeshwagh/NLUAssignment2.git
```

2. Open the notebook.

```
NLUAssignment2.ipynb
```

3. Run all notebook cells sequentially.

4. After execution, the notebook will:

- Train the Seq2Seq model
- Evaluate BLEU Score
- Evaluate Rescaled BERTScore
- Measure inference time
- Count trainable parameters
- Generate **submission.csv**

---

## Results

The developed Seq2Seq Attention model successfully generates Sanskrit-to-English translations and provides a reproducible baseline implementation for Neural Machine Translation. Although the translation quality is limited due to the low-resource nature of Sanskrit and the use of greedy decoding, the implementation demonstrates the complete NMT pipeline from preprocessing to evaluation.

---

## Future Improvements

- Beam Search Decoding
- Transformer Architecture
- Byte Pair Encoding (BPE)
- Larger Parallel Corpus
- Pretrained Multilingual Models
- Regularization to reduce overfitting

---

## References

1. Papineni, K., Roukos, S., Ward, T., & Zhu, W. (2002). *BLEU: A Method for Automatic Evaluation of Machine Translation*. ACL.

2. Zhang, T., Kishore, V., Wu, F., Weinberger, K. Q., & Artzi, Y. (2020). *BERTScore: Evaluating Text Generation with BERT*. ICLR.

3. PyTorch Documentation  
   https://pytorch.org/docs/stable/

4. NLTK Documentation  
   https://www.nltk.org/

5. Assignment 2 – Sanskrit-to-English Neural Machine Translation, Natural Language Understanding.

---

## Author

**Rishikesh Wagh**

**Roll No:** G25AIT1138

Natural Language Understanding

Indian Institute of Technology Jodhpur
