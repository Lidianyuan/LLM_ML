# Prompt Engineering Accelerates the Data-Driven Discovery of Photocatalysts via an LLM-Based Mixture-of-Experts Strategy  
> Automated extraction of scientific information from literature using multiple large language models (LLMs), applied to photocatalytic hydrogen evolution based on graphitic carbon nitride.  

---

##  Overview    
This project explores the use of **large language models (LLMs)** for automated information extraction from scientific literature.  
Focusing on **graphitic carbon nitride (g-C₃N₄) photocatalytic hydrogen production**, multiple LLMs were employed to extract key experimental data and metadata from research papers.  
The extracted information was curated into a **high-quality dataset**, which was then used for **machine learning modeling and analysis** to support experimental design and parameter optimization.  

---

##  Main Features  

1. **Document Processing**  
   - Automatically convert `.docx` (Word) files to `.pdf`;  
   - Merge main PDF documents with their supporting information;    
    *Please prepare the target-domain literature documents in advance before running these steps.*  

2. **Automated Information Extraction**  
   - Use a large language model to extract structured data from research papers;  
   - The workflow originally used multiple (≈10) models, but only one example implementation is included here;  
   - Uses `selenium` for automated browser control;   
   - Some file paths and configurations need manual updates depending on your environment.  
    *This means you may need to manually specify the correct ChromeDriver or FirefoxDriver path, and adjust input/output directories to match your local setup.*  

3. **Data Preprocessing**  
   - Clean and normalize extracted data;  
   - Handle missing and inconsistent values;  
   - Generate machine-learning-ready features.  

4. **Machine Learning Modeling**  
   - Train ML models to analyze relationships between experimental parameters and photocatalytic performance;
   - Multiple models were tested, but only one example implementation is provided.  

5. **Environment Configuration**  
   - Includes a `requirements.txt` file for easy dependency installation.  
