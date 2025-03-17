# 🧠 GPT-4 Mental Health Text Classification

## 📌 Project Overview
This project leverages **GPT-4-Turbo** to classify mental health-related text statements into predefined categories such as **Normal, Depression, Anxiety, Suicidal, Bipolar, Stress, and Personality Disorder**. Instead of traditional machine learning, we use **few-shot learning** with **real examples** directly in the prompt, improving accuracy without requiring fine-tuning.

## 🎯 Objective
- Automatically classify mental health-related text into categories.
- Improve classification accuracy using **few-shot learning and Chain-of-Thought (CoT) prompting**.
- Optimize GPT-4's output through **post-processing and error correction**.

---

## 📂 Dataset
The dataset consists of **mental health-related statements** labeled with categories such as:
- **Normal** → No signs of mental distress.
- **Depression** → Feelings of sadness, hopelessness, and lack of motivation.
- **Anxiety** → Overthinking, excessive worry, and nervousness.
- **Suicidal** → Mentions of self-harm or thoughts of ending life.
- **Bipolar** → Extreme mood swings between high energy and deep sadness.
- **Stress** → Feeling overwhelmed or struggling with external pressure.
- **Personality Disorder** → Instability in emotions, thoughts, or behaviors.

## 🛠️ Tech Stack
- **Language Model:** OpenAI GPT-4-Turbo
- **Programming Language:** Python
- **Frameworks & Libraries:** OpenAI API, Pandas, Scikit-learn
- **Deployment:** Jupyter Notebook/Google Colab

---

## 🔹 Implementation Steps
### 1️⃣ Data Preprocessing
- Load dataset, clean text, and handle missing values.
- Check class distribution and balance data if necessary.

### 2️⃣ Few-Shot Learning with GPT-4
- Dynamically inject **real examples** into the prompt.
- Use **Chain-of-Thought (CoT) reasoning** to improve classification.

### 3️⃣ Post-Processing for Error Correction
- Apply rule-based corrections to improve classification accuracy.

### 4️⃣ Model Evaluation
- Compute accuracy using a **100-sample subset**.
- Compare results before and after post-processing.

---

## 🚀 How to Run
1. **Install OpenAI SDK** (if not installed):
   ```bash
   pip install openai
   ```
2. **Set up OpenAI API key:**
   ```python
   import openai
   openai.api_key = "your_api_key_here"
   ```
3. **Run the classification script:**
   ```python
   df_sample["predicted_status"] = df_sample["statement"].apply(lambda x: classify_with_few_shot_optimized(x, df))
   ```
4. **Evaluate accuracy:**
   ```python
   from sklearn.metrics import accuracy_score
   accuracy = accuracy_score(df_sample["status"], df_sample["predicted_status"])
   print(f"Model Accuracy: {accuracy:.2%}")
   ```

---

## 🔍 Conclusion
This project demonstrates the effectiveness of **few-shot learning and Chain-of-Thought (CoT) prompting** for classifying mental health-related statements using **GPT-4-Turbo**. By leveraging real examples dynamically in prompts and applying post-processing corrections, we achieved improved classification accuracy without requiring fine-tuning. This approach provides a **scalable, efficient, and adaptable** solution for AI-powered mental health analysis.

Further improvements could involve **fine-tuning GPT models on a larger dataset** or integrating **hybrid approaches** using traditional machine learning models for enhanced robustness.

