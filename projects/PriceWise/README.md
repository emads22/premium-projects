# PriceWise

<img src="screenshots/PriceWise-1.png" alt="PriceWise_logo" width="300">

## Overview

**PriceWise** is an AI-powered deal discovery platform that leverages machine learning and intelligent data retrieval to analyze e-commerce pricing trends. The application continuously monitors and fetches deals from multiple online sources, predicts fair pricing using AI models, and presents users with the best-discounted offers available. With its automated workflow, PriceWise ensures users stay ahead of price fluctuations and capitalize on the best opportunities.

The application runs in **real-time**, operating on a **5-minute cycle** to fetch and analyze the latest deals. Users can interact with the Gradio UI to view the most recent findings, and clicking on any deal in the UI triggers an automatic **Pushover notification**, alerting the user about the specific deal.

---

## Features
- 🔍 **AI-Powered Deal Discovery**: Uses advanced Language Models (LLMs) to predict and analyze the best deals online.
- ⏳ **Automated Ticking System**: Runs continuously every **5 minutes**, scanning and updating deals automatically.
- 📊 **Real-Time Price Monitoring**: Tracks pricing changes across multiple e-commerce platforms and logs trends.
- 🛒 **Transparent Price Analysis**: Displays product details, estimated fair prices, and calculated discounts.
- 🔔 **Smart Alerts via Pushover**: Clicking on any deal in the UI automatically sends a push notification to the user.
- 📈 **Historical Price Trends**: Analyzes past pricing data to predict future trends and highlight the best savings.
- 🔐 **Secure & Private**: API keys and sensitive credentials are stored securely in a `.env` file.

---

## AI-Powered Agents
PriceWise utilizes a system of **7 intelligent agents** that work together to scan, predict, and refine deal evaluations:

### **1. Fetcher Agent**
- **Purpose:** An AI-powered agent that scrapes, selects, and summarizes the most detailed and clearly priced deals from RSS feeds.
- **Functionality:**
  - Scrapes deals from user-defined **RSS feeds**.
  - Cleans and extracts relevant price information.
  - Uses **OpenAI** to ensure valid prices.
  - Converts structured deal data into a **custom Pydantic model**.
  - Fetches deals from RSS feeds following predefined entry limits.
  
### **2. OpenAI Agent**
- **Purpose:** Predicts product prices using OpenAI's model.
- **Functionality:**
  - Searches for similar products in a **prebuilt local vector database (RAG)**.
  - Generates an estimated price based on **product similarities and contextual data**.
  
### **3. PriceGen Agent**
- **Purpose:** A fine-tuned private LLM that provides accurate price estimations.
- **Functionality:**
  - Hosted on **Hugging Face** and deployed via **Modal**.
  - Trained and monitored for price prediction accuracy.
  - Acts as a dedicated endpoint for retrieving item price estimations.
  
### **4. Fusion Agent**
- **Purpose:** An AI-driven agent that fuses predictions from multiple models.
- **Functionality:**
  - Uses a **trained Linear Regression model** to generate final price estimates.
  - Incorporates predictions from **OpenAI Agent and PriceGen Agent**.
  - Evaluates minimum and maximum price variations to build weighted calculations.
  
### **5. Pushover Agent**
- **Purpose:** Sends **real-time push notifications** to users via **Pushover API**.
- **Functionality:**
  - Alerts users when a **top deal is found**.
  - Clicking on any deal (row) in the UI **automatically sends a Pushover notification**.
  - **Users must sign up for a Pushover account** at [Pushover.net](https://pushover.net/) and obtain API credentials.

### **6. Orchestrator Agent**
- **Purpose:** Manages the entire deal evaluation workflow.
- **Functionality:**
  - Scans and fetches new deals every **5 minutes**.
  - Processes deals through the **FetcherAgent**.
  - Predicts prices using the **Fusion model**.
  - Notifies the user if a **valid top deal is found**.
  - Prevents reprocessing of already saved deals.
  - If no valid deals are found, no notification is sent.

---

## Setup 

### Clone the Repository
```bash
git clone https://github.com/emads22/PriceWise.git
cd PriceWise
```

### Install Dependencies
Navigate to the project directory and activate the provided Conda environment to ensure all dependencies are installed:

```bash
conda env create -f pricewise_env.yml
conda activate pricewise
```

### Set Up API Keys
Create a `.env` file in the root directory and add the required API keys:
```env
OPENAI_API_KEY=your_openai_api_key
PUSHOVER_USER=your_pushover_user
PUSHOVER_TOKEN=your_pushover_token
```
Ensure all required environment variables are set before launching the app.

---

## Usage

To start the PriceWise application, run:
```bash
python pricewise.py
```
### **How It Works:**
- **Runs automatically every 5 minutes** to scan, fetch, and analyze deals.
- **Displays the logging process dynamically in colorful format** within the UI.
- **Shows saved deals in a DataFrame** that updates in real-time.
- **Clicking on any deal row triggers an automatic push notification** via Pushover.
- **Logs are saved to a file** for backup and analysis.
- **Deals are stored in ChromaDB by default**, but there is an option to store them in a **JSON file** using dedicated methods for reading and writing.
- **To visualize or take a snapshot of the current saved deals**, run:
    ```bash
    python deal_coordinator.py
    ```
    This will generate a **JSON file** in the current directory, containing an **organized list of top saved deals** in a structured format.

---

## Model Training & Deployment
Certain components of **PriceWise** require additional **custom training and setup**:
- **Training the private PriceGen model** on a curated dataset.
- **Deploying the fine-tuned model to Modal for live API usage**.
- **Training the Fusion Model** to optimize price prediction accuracy.
- **Creating and updating the ChromaDB vectorstore** to enhance deal evaluations.

🔹 For details, elaboration, or access to these components, **contact me directly**.

---

### ⬅ [🔗 Back to Premium Projects](../../README.md#-ai-and-llm-solutions)
