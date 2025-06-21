# 📊 Capstone Project Data Analytics Program – IBM Granite

Welcome to the **Capstone Project Data Analytics Program** repository!
This project contains two labs utilizing the **IBM Granite large language model** via **Replicate API** to automate:

1. ✅ **Customer Review Sentiment Classification**
2. 🧠 **Meeting Transcript Summarization**

Both labs are executed using **Google Colab**, focusing on productivity and clarity for internal decision-making at **Capstone Project**, a mid-sized smartphone company.

---

## ⚖️ Lab 1: Prompt an IBM Granite Model to Classify and Summarize Data

### 🌟 Objective

Automate the classification of customer reviews and summarization of weekly cross-functional meetings using IBM Granite (`granite-3.0-8b-instruct`).

### 🧪 Tasks

* Classify reviews into: `positive`, `negative`, or `mixed`
* Tag reviews with focus areas: `battery life`, `screen quality`, `performance`
* Summarize long meeting transcripts into structured, actionable insights

### 📂 Input Examples

* **Review:** `"Battery dies in 4 hours but screen is amazing"`
* **Meeting Transcript:** Raw conversation logs from product & marketing meetings

### 📈 Output Format

* **Review Classification:**

```json
{
  "sentiment": "mixed",
  "tags": ["battery life", "screen quality"]
}
```

* **Meeting Summary:**

```
Key Decisions:
- Launch date delayed to Q3

Action Items:
- Marketing to revise campaign strategy by Monday

Priorities:
- Improve battery optimization for next firmware update
```

---

## ⚙️ Lab 2: Adjust IBM Granite Parameters to Refine the Output

### 🌟 Objective

Improve the **accuracy**, **consistency**, and **structure** of classification and summarization by tuning prompt parameters.

### 📊 Parameters Tuned

| Parameter            | Purpose                             |
| -------------------- | ----------------------------------- |
| `max_tokens`         | Limit the response length           |
| `top_k`              | Top-k sampling for token generation |
| `top_p`              | Nucleus sampling (top-p sampling)   |
| `repetition_penalty` | Prevent repeated phrases            |
| `stopping_sequence`  | Define stopping points for response |

### ⚡ Example Prompt Adjustment

```python
response = model.predict(
    input="Summarize the following meeting transcript...",
    max_tokens=300,
    top_p=0.9,
    top_k=50,
    repetition_penalty=1.2,
    stopping_sequences=["--END--"]
)
```

---

## 🚀 Setup Instructions

### ✅ Requirements

* Google Account (for Colab)
* [Replicate](https://replicate.com/) account with API token
* Required Python packages:

```bash
pip install replicate langchain_community
```

### 🔑 Environment Variable

Store your Replicate API token securely:

```python
import os
os.environ["REPLICATE_API_TOKEN"] = "your-token-here"
```

---

## 📁 Files Included

| File                               | Description                            |
| ---------------------------------- | -------------------------------------- |
| `classification_lab1.ipynb` | Prompt to clasify and summarize data    |
| `classification_lab2.ipynb`       | adjust the parameters to refine the output       |

---
