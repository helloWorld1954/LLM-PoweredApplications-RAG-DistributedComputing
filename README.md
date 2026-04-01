# Assignment 3 — Distributed Analytics, RAG, and Integrated Query Application

This repository contains the implementation for **Assignment 3**, which combines distributed data processing with Apache Spark, document retrieval with a RAG pipeline, and an integrated natural-language analytics interface over NYC transportation data and transportation-related documents.

## Repository Structure

```text
.
├── Assignment3.1.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── docs/
    ├── 01_tlc_annual_report_2024.pdf
    ├── 02_fhv_license_review_feb2025.pdf
    ├── 03_tlc_factbook_2020.pdf
    ├── 04_parrott_reich_driver_earnings_2018.pdf
    ├── 05_driver_expense_model_2024.pdf
    ├── 06_electrification_in_motion_2024.pdf
    ├── 07_cbd_tolling_ea_exec_summary.pdf
    ├── 08_fare_play_congestion_pricing_ibo.pdf
    ├── 09_nber_congestion_pricing_effects_2025.pdf
    ├── 10_predicting_taxi_pickups.pdf
    └── README.md
```

## Assignment Overview

The notebook is organised into three major parts:

### Part 1 — Distributed Data Processing with Spark
- Creates and configures a local Spark session
- Loads NYC Yellow Taxi trip data
- Cleans the dataset and engineers features
- Runs Spark SQL analytics
- Explains optimisation choices and execution plans

### Part 2 — Retrieval-Augmented Generation (RAG) Pipeline
- Builds a PDF corpus over transportation documents
- Loads and chunks documents
- Stores embeddings in ChromaDB
- Retrieves relevant chunks for natural-language questions
- Evaluates retrieval quality and analyses failure cases

### Part 3 — Integrated Analytics Application
- Routes user questions into **DATA**, **DOCUMENT**, or **HYBRID**
- Generates SQL for structured analytics queries
- Uses retrieved context for document-based questions
- Demonstrates an end-to-end natural language interface

## Setup Instructions

### 1. Create and activate a virtual environment

#### macOS / Linux
```bash
python3 -m venv .venv
source .venv/bin/activate
```

#### Windows
```bash
python -m venv .venv
.venv\Scripts\activate
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Prepare the data and document folders

Place the following files in the correct locations before running the notebook:

- **NYC Yellow Taxi trip data** in your chosen data folder if you are not downloading it programmatically
- **PDF corpus** inside the `docs/` directory

The notebook originally references a `documents/` folder. For final repository submission, either:

- rename `docs/` to `documents/`, or
- update the notebook paths from `documents/` to `docs/`

Recommended option for consistency: update the notebook to use `docs/`.

### 4. Configure API access

The integrated RAG and routing sections use an OpenAI-compatible client.

Set your credentials as environment variables instead of hardcoding them:

#### macOS / Linux
```bash
export OPENAI_API_KEY="your_api_key"
export OPENAI_BASE_URL="your_base_url"
```

#### Windows PowerShell
```powershell
$env:OPENAI_API_KEY="your_api_key"
$env:OPENAI_BASE_URL="your_base_url"
```

## How to Run

### Option 1 — JupyterLab
```bash
jupyter lab
```

Then open:

```text
Assignment3.1.ipynb
```

Run the notebook from top to bottom.

### Option 2 — Jupyter Notebook
```bash
jupyter notebook
```

## Notes for Grading

This repository includes:
- an updated `README.md`
- a `requirements.txt` file with the notebook dependencies
- a `.gitignore` that excludes cache files, datasets, and model/vector artifacts
- a `docs/` directory layout for the PDF corpus

