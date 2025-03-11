# DataSynth: AI-Powered Synthetic Dataset Generator  

<img src="../../logos/DataSynth_logo.png" alt="DataSynth_logo" width="200">

## Overview  
DataSynth is an **AI-driven tool** designed to generate **high-quality structured synthetic datasets** using multiple **large language models (LLMs)**. Whether you're an **AI researcher, data scientist, or developer**, DataSynth provides a seamless way to create datasets tailored to your specific needs. It offers a **user-friendly web interface** powered by **Gradio**, allowing flexible and efficient dataset generation.

### **Key Features**  
- **Automates dataset creation**, eliminating the need for manual data collection.  
- **Supports multiple LLMs**, including **OpenAI GPT, Claude, Gemini, Meta-LLaMA, and Qwen** for diverse dataset generation.  
- **Intuitive web-based UI** for real-time dataset customization and preview.  
- **Customizable dataset formatting**, enabling users to define fields, structures, and values according to their specific requirements.  
- **Scalable and efficient**, capable of handling large-scale dataset generation with optimized performance.  
- **Designed for research and development**, helping in training AI models, validating hypotheses, and conducting simulations.  

### **How It Works**  
1. **Choose an LLM**: Select from the supported models to generate your dataset.  
2. **Define Your Dataset**: Specify the structure, fields, and data constraints for accurate dataset generation.  
3. **Generate & Preview**: Use the **Gradient UI** to generate, refine, and preview your dataset in real time.  
4. **Export & Store**: Save your dataset as a **JSON file** for easy access and future use.  

### **Why Choose DataSynth?**  
- **Saves time and effort** by automating dataset creation.  
- **Ensures high-quality, structured, and realistic synthetic data.**  
- **Flexible customization** to suit different AI and data science applications.  
- **User-friendly interface** that simplifies the process for both beginners and advanced users.  
- **Supports multiple LLMs**, providing diverse outputs tailored to specific use cases.  

DataSynth empowers researchers and developers to **build, refine, and expand their AI training datasets effortlessly**, making it an essential tool in AI and data science workflows.

---

## Features  

### **Gradio-Based Application**  
- **Gradient UI**: A web interface for dataset generation.  
- **Multi-Model Support**: Choose from **GPT, Claude, Gemini, LLaMA, and Qwen** for dataset creation.  
- **One-Shot Learning**: Provide a single example to guide dataset generation.  
- **Real-Time Streaming**: Generates and displays data **dynamically** as it is processed.  
- **Easy Export & Storage**: Save generated datasets in **JSON format** with structured fields inside `generated_datasets` directory.  

### **Notebook-Based Dataset Generation**  
For users who prefer Jupyter notebooks, DataSynth includes two Colab-compatible notebooks inside `assets/study` directory:  
| Notebook | Description |
|-------------|----------------|
| `study/datasynth.ipynb` | General-purpose dataset generator. |
| `study/datasynth_multishot.ipynb` | Uses multi-shot learning to refine dataset generation. |  

---

## Setup & Installation  

### **1. Clone the Repository**  
```bash
git clone https://github.com/emads22/DataSynth.git
cd DataSynth
```

### **2. Install Dependencies**  
Install dependencies from the environment file:  
```bash
conda env create -f datasynth_env.yml
conda activate datasynth
```

### **3. Configure API Keys & Endpoints**
Before running the application, **add your API keys and personal endpoint URLs** to the `.env` file. This file manages authentication details for different LLM providers.

Create or update the `.env` file with the following variables:
```python
OPENAI_API_KEY = "your_openai_api_key"
CLAUDE_API_KEY = "your_claude_api_key"
GEMINI_API_KEY = "your_gemini_api_key"
LLAMA_API_ENDPOINT = "your_custom_llama_endpoint"
QWEN_API_ENDPOINT = "your_custom_qwen_endpoint"
HF_TOKEN = "your_hf_token"
```
- Ensure that the `.env` file remains **secure** and is not shared publicly.
- Additionally, if you are using **private Hugging Face endpoints**, make sure they are **running and not paused** before launching the application.

---

## Running the Gradio App  

### **Run the Application**  
```bash
python datasynth.py
```
This launches an interactive **web UI** where users can **customize dataset parameters** and **generate structured JSON outputs**.

---

## Running the Jupyter Notebooks  

### **Option 2: Open in Google Colab**  
- [Open datasynth.ipynb](https://colab.research.google.com/drive/1XJdCKjCq77V1mf2-XDMNnlhwrT2drRh0)  
- [Open datasynth_multishot.ipynb](https://colab.research.google.com/drive/1tzjf86bR-P2_RBGet8i0WSsKALgs1bP9)  

**Steps to run the notebooks:**  
1. Open the desired notebook in Colab.  
2. Go to **Runtime** → **Change runtime type** → Select **GPU** (`T4` or higher).  
3. Install dependencies:  
   ```python
   !pip install -q requests torch bitsandbytes transformers sentencepiece accelerate openai httpx==0.27.2 gradio
   ```
4. (Optional) Mount Google Drive for persistent storage:  
   ```python
   from google.colab import drive
   drive.mount("/content/drive")
   ```

---

## Usage Guide  

### **Using the Gradio UI**  
1. **Launch the app** using `python datasynth.py`.  
2. **Select a dataset subject** (e.g., "Job Postings", "Customer Reviews").  
3. **Choose the number of samples** to generate.  
4. **Select an AI model** (GPT, Claude, Gemini, etc.).  
5. **(Optional) Provide a sample structure** for the AI to follow.  
6. Click **"Generate Synthetic Data"** and receive structured JSON output.  

### **Using the Notebooks**  
1. **Run the notebook** in Colab.  
2. **Define dataset parameters** inside the notebook cells.  
3. **Generate datasets** dynamically with model-based guidance.  
4. **Export results** to local storage or Google Drive.  

---




