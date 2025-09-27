# 🏆 Kaggle-LMSYS Competition: Chatbot Arena Human Preference Predictions

This competition challenges participants to **predict which chatbot response users will prefer** in a head-to-head match between LLMs.  
The dataset comes from **Chatbot Arena**, where different models generate responses to user queries.  

The goal is to develop ML models that **better align LLMs with human preferences** and improve chatbot-human interaction.  

---

## 🚀 Approach

I fine-tuned LLMs using **QLoRA (Low Rank Adaptation)** to predict human preferences.  
The workflow consisted of **training two large models** and combining their predictions.

### 1. Data Splitting  
- Randomly split **20%** of the dataset into train/validation.  
- Validation results were used for hyperparameter tuning.  

### 2. Model Selection  
- **gemma-2-9b**  
  - Training corpus closely matched the competition data distribution.  
  - Convenient quantization → **faster training**.  
- **llama-3.1-8b**  
  - Strong benchmark performance.  
  - **8B version** offered efficient inference.  

### 3. Fine-tuning  
- Conducted multiple experiments by varying:  
  - Learning rate  
  - Freezing layers  
  - Prompt input length  
- Selected **weights with the highest validation score**.  

### 4. Ensembling  
- Predictions from the two models were **weighted and combined**.  
- Weights were tuned based on **online leaderboard scores**.  

---

## 🏅 Result

- **Silver Medal** 🎖️  
- Final Rank: **52 / 1803** participants  

<p align="center">
  <img width="800" alt="Kenmook - LMSYS - Chatbot Arena Human Preference Predictions" src="https://github.com/user-attachments/assets/f7958c80-8668-4494-a985-80fdf8fa1e4d" />
</p>

