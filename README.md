# 🤖 AI Text Authorship Estimator

This Python tool analyzes `.txt`, `.docx`, `.pdf`, and `.pptx` files to estimate how likely a given text is written by an AI. It scores each sentence individually and generates an overall verdict about whether the text was likely written by a human, AI, or a combination of both.

---

## 🧠 What It Does

- Analyzes text files for **AI-like writing patterns**
- Scores each sentence from 0–100% based on:
  - Sentence complexity
  - Readability (Flesch Reading Ease)
  - Lexical diversity
  - Overuse of conjunctions
- Gives a **verdict per sentence**:  
  - ✅ Human-like  
  - 🟡 Possibly AI-assisted  
  - ⚠️ Likely AI-generated
- Reports a **summary decision** about the entire text

---

## 📂 Supported File Types

- `.txt`
- `.docx` (Word)
- `.pdf` (text-based only)
- `.pptx` (PowerPoint)

> ❗ Legacy `.doc` and `.ppt` files are not supported. Convert them to `.docx` or `.pptx`.

---

## 🚀 Installation

Install Python packages:

```bash
pip install spacy textstat pdfplumber python-docx python-pptx
python -m spacy download en_core_web_sm

## ⚙️ Usage

python AIchecker.py path/to/your_file.docx

## 🧾 Example Output

🧠 Estimated AI-style writing: 58.3% of the text.

⚠️ Likely AI-written (71%) → It is important to note that we utilized...
🟡 Possibly AI-supported (53%) → Moreover, such strategies often contribute...
✅ Likely Human (33%) → I had never thought of that before. It just made sense.

--- Summary Report ---
Total sentences analyzed: 12
Average AI-likeness score : 58.3%
✅ Human-like sentences   : 4
🟡 Possibly AI-supported  : 5
⚠️ AI-like sentences      : 3

🧠 Final verdict: This text is possibly AI-assisted.

##🧪 How It Works
The scoring function uses a heuristic-based approach:

Sentence Length → Longer, complex sentences often signal AI text

Conjunction Density → Overuse of “however”, “thus”, “in order to”

Lexical Diversity → Low variation = robotic

Readability → AI tends to generate mid-level readable content

Each sentence is classified with thresholds:

0.00–0.45 → ✅ Human

0.46–0.65 → 🟡 Possibly AI-assisted

0.66–1.00 → ⚠️ Likely AI-generated
