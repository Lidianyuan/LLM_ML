# Prompt Engineering Accelerates the Data-Driven Discovery of Photocatalysts via an LLM-Based Model Ensemble Strategy  
> Automated extraction of scientific information from literature using multiple large language models (LLMs), applied to photocatalytic hydrogen evolution based on graphitic carbon nitride.  

---

## Overview

This project applies **large language models (LLMs)** to automate the extraction of experimental information from scientific literature.  
The case study focuses on **graphitic carbon nitride (g-C₃N₄) photocatalytic hydrogen evolution**, where multiple LLMs were used to extract structured information from research papers.  
After information extraction, the data were **curated, preprocessed, and modeled** using traditional machine learning techniques to analyze structure–performance relationships and support experimental optimization.

The provided notebooks demonstrate the full process from document preparation to model training.

---

##  Workflow Overview

1. **Document Preparation** — Prepare domain-specific research articles in `.docx` or `.pdf` format.  
2. **Conversion and Merging** — Convert `.docx` files to `.pdf`, then merge the main paper and supporting information.  
3. **Automated Information Extraction** — Use a large language model (ChatGLM example provided) to extract structured data automatically.  
4. **Data Preprocessing** — Clean, normalize, and format the extracted information.  
5. **Machine Learning Analysis** — Train ML models to analyze and predict photocatalytic performance.  

Each notebook corresponds to one key stage of this workflow.

---

##  Main Files and Their Functions

### 1. `WORDtoPDF.ipynb`
Converts `.docx` (Word) files into `.pdf`.  
⚠️ Please prepare all research papers in advance and store them in a folder such as `./literature/`.  
Output PDFs are saved in `./converted_pdfs/`.

---

### 2. `PDFmerging.ipynb`
Merges the main text and supporting information PDFs into a single file for each paper.  
This step ensures a consistent document structure for later information extraction.  
Output files are stored in `./merged_pdfs/`.

---

### 3. `ChatGLM.ipynb`
Uses an **LLM (ChatGLM)** to automatically extract experimental parameters and results from merged PDFs.  
The extraction logic can be adapted to other models as needed.  

**Important:**  
- This script uses `selenium` for browser-based automation.  
- Update file paths and the ChromeDriver (or FirefoxDriver) path before running.  
  Example:
  ```python
  driver = webdriver.Chrome(executable_path="C:/path/to/chromedriver.exe")
  The extracted data (e.g., JSON or CSV format) are saved in ./data/extracted/.

### 4. `preprocess.ipynb`

Cleans and standardizes the raw data extracted by the LLM.
This notebook performs:

Duplicate removal

Missing-value handling

Normalization and feature engineering
...
Input: ./data/extracted/
Output: ./data/cleaned/cleaned_data.csv

### 5. `ML.ipynb`

Trains a sample machine learning model using the cleaned dataset.
Only one representative model  is provided here, but the framework supports multiple algorithms.
The notebook includes:

Model training and evaluation

Visualization of performance metrics

Parameter adjustment examples

Output: ./results/ (contains figures, metrics, and optionally model files)

### 6. `requirements.txt`

Lists all required Python dependencies.
Install them using:

pip install -r requirements.txt


For best compatibility, use Python ≥3.9 (Anaconda environment recommended):

conda create -n llm-photocatalysis python=3.10
conda activate llm-photocatalysis

🧭 Tips for Reproduction

Run the notebooks in the following order:
1️⃣ WORDtoPDF.ipynb
2️⃣ PDFmerging.ipynb
3️⃣ ChatGLM.ipynb
4️⃣ preprocess.ipynb
5️⃣ ML.ipynb

Keep consistent folder names and file paths throughout all notebooks.

For large document sets, process files in batches to avoid performance issues.

If selenium fails to start the browser, ensure that your ChromeDriver matches your Chrome version.

🧩 Summary

This repository provides a complete end-to-end workflow from unstructured literature to data-driven machine learning insights.
It integrates multiple AI techniques — including LLM-based information extraction and ML modeling — for accelerating materials discovery and scientific data collection.
