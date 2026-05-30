# Nanlyst: NIM-Powered Data Agent

**Nanlyst** is an autonomous AI data analysis agent powered by NVIDIA NIM (Llama 3.1). It monitors a local directory, processes raw data files, performs deep statistical analysis, scrapes the web for missing context, and generates professional-grade Excel reports with automated visualizations.

![Status](https://img.shields.io/badge/System-Functional-00ff88?style=for-the-badge)
![NIM](https://img.shields.io/badge/NVIDIA-NIM-76b900?style=for-the-badge&logo=nvidia)

## Features

- **Automated Pipeline**: Monitors `./data/inbox/` for new CSV, JSON, XLSX, or Parquet files.
- **AI Analysis**: Uses NVIDIA NIM to identify trends, outliers, and insights.
- **Professional Reporting**: Generates fully formatted `.xlsx` workbooks including:
  - Executive Summaries
  - Data Quality Reports
  - Correlation Matrices & Statistical Breakdown
  - Auto-generated Matplotlib/Seaborn charts.
- **Web Research & Scraping**: Can scrape the web to find emails, site titles, and contact info for lead lists or company data.
- **Dataset Generator**: Generate entirely new datasets from natural language prompts.
- **Live Dashboard**: Real-time monitoring of system metrics (CPU/RAM/GPU), active agent logs, and task history via a Socket.IO web interface.

## Quick Start

### 1. Prerequisites
- Python 3.9+
- An NVIDIA NIM API Key ([Get one here](https://build.nvidia.com/explore/discover))

### 2. Installation
```bash
# Clone the repository
git clone https://github.com/YourAlias/nanlyst.git
cd nanlyst

# Install dependencies
pip install -r requirements.txt
```
3. Configuration
Export your API key as an environment variable:
```bash
export NIM_API_KEY="your_key_here"
```
4. Run the Agent
```bash
python agent.py
```
Access the dashboard at: http://localhost:5050

# How to Use
Analysis: Drop any supported data file into the ./data/inbox/ folder. The agent will detect it instantly.
Generation: Navigate to the Dataset Generator tab on the dashboard to build new data from scratch.
Results: Check ./data/results/ for your formatted Excel reports.

# Project Structure
agent.py: The core logic, AI agent, and Flask dashboard.
  data/: (Created on first run)
    inbox/: Place raw data here.
    results/: Completed Excel reports.
    processed/: Archive of analyzed files.
    failed/: Error logs and files that couldn't be processed.
logs/: Internal agent logs.

# Tech Stack
LLM: Llama 3.1 70B (via NVIDIA NIM)
Backend: Python, Flask, Socket.IO
Data: Pandas, Numpy, Scipy
Visualization: Matplotlib, Seaborn
Excel: OpenPyXL

# Disclaimer
This project is an independent tool using NVIDIA NIM APIs. Use of the web scraper should comply with the Target's robots.txt and Terms of Service. Generated data is AI-produced and should be verified for critical applications.
Developed by @Void-ShadeCoding
