# Agentic AI Security Pull Request Mining Project

This project analyzes security-related tasks performed by agentic AI tools by mining automatically-generated pull requests from a HuggingFace dataset.  
The work includes processing four dataset tables and generating a final merged output identifying security-related PRs.

This repository contains:

- Python scripts for Tasks 1 through 5  
- Generated CSV output files for each task, as required by the rubric  

---

## 📌 Project Structure

security-agentic-ai-mining/
├── task1.py
├── task2.py
├── task3.py
├── task4.py
├── task5.py
├── task1_output.csv
├── task2_output.csv
├── task3_output.csv
├── task4_output.csv
└── task5_output.csv
Each Python file corresponds to one task, and each CSV file is the output produced by running that task.

---

## 🧪 Task Descriptions

### **Task 1 — Pull Request Metadata Extraction**
**Script:** `task1.py`  
**Input:** `all_pull_request.csv`  
**Output:** `task1_output.csv`  

Extracted and renamed columns:
- TITLE  
- ID  
- AGENTNAME  
- BODYSTRING  
- REPOID  
- REPOURL  

---

### **Task 2 — Repository Metadata Extraction**
**Script:** `task2.py`  
**Input:** `all_repository.csv`  
**Output:** `task2_output.csv`

Extracted and renamed columns:
- REPOID  
- LANG  
- STARS  
- REPOURL  

---

### **Task 3 — PR Classification Metadata Extraction**
**Script:** `task3.py`  
**Input:** `pr_task_type.csv`  
**Output:** `task3_output.csv`

Extracted and renamed columns:
- PRID  
- PRTITLE  
- PRREASON  
- PRTYPE  
- CONFIDENCE  

---

### **Task 4 — Commit Details Extraction**
**Script:** `task4.py`  
**Input:** `pr_commit_details.csv`  
**Output:** `task4_output.csv`

Extracted and renamed columns:
- PRID  
- PRSHA  
- PRCOMMITMESSAGE  
- PRFILE  
- PRSTATUS  
- PRADDS  
- PRDELSS  
- PRCHANGECOUNT  
- PRDIFF (cleaned diff/patch text to remove special characters)

---

### **Task 5 — Final Merged Output & Security Classification**
**Script:** `task5.py`  
**Inputs:**  
- `task1_output.csv`  
- `task3_output.csv`  

**Output:** `task5_output.csv`

Final columns:
- ID  
- AGENT  
- TYPE  
- CONFIDENCE  
- SECURITY (1 = security-related PR, 0 = not security-related PR)

Security detection is based on keyword matching in the PR title and body using a defined keyword list.

---

## ▶️ Running the Code

Make sure you have Python installed along with `pandas`:

```bash
pip install pandas
