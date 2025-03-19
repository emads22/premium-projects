
# MeetingRecap

<img src="screenshots/MeetingRecap-1.png" alt="MeetingRecap_logo" width="300">

## Overview
**MeetingRecap** is a fully-fledged Python application designed to automatically generate detailed meeting minutes from audio recordings. It uses OpenAI's `Whisper` model for high-quality speech-to-text conversion and Meta's `LLaMA` model for summarizing transcripts into well-structured meeting minutes. The app is equipped with a **Gradio** interface for easy interaction, allowing users to upload audio files and quickly retrieve clear, concise meeting summaries in markdown format.

The application is organized into an environment-based setup, making it portable and easy to deploy in different configurations. Additionally, **logging** functionality is implemented to track significant steps and errors during the process. The app can be run locally or deployed in Docker for scalable usage.

There is also an accompanying **Jupyter Notebook** located in the `study` folder. This notebook serves as a **study and structuring phase**, helping you understand and prepare the application before implementing it into the production environment.

---

## Features
- **Speech-to-Text Conversion**: Converts MP3 meeting recordings into text using OpenAI's `Whisper` model.
- **Summarization with Custom Models**: Utilizes the `LLaMA` model for generating detailed meeting minutes. You can also choose other models compatible with Hugging Face's `transformers` library.
- **Persistent Model Storage**: Models can be saved for future reuse, either on Google Drive or in a temporary storage.
- **Gradio User Interface**: A clean and intuitive UI for uploading audio files and retrieving meeting minutes in markdown format.
- **Logging**: Every major step in the process is logged for traceability, including transcription and generation success or failure.
- **Environment Setup**: Uses environment variables for configuring sensitive data like OpenAI API keys and model storage paths.
- **Study Folder**: A dedicated Jupyter Notebook (`study/`) for learning, exploring, and structuring the application before production use.

---

## Setup
1. **Clone the repository** and set up the environment:
   - Clone the repository:
     ```bash
     git clone https://github.com/emads22/MeetingRecap.git
     cd MeetingRecap
     ```

2. **Create the Conda environment** and install the dependencies:
   - Create the Conda environment from `meetingrecap_env.yml`:
     ```bash
     conda env create -f meetingrecap_env.yml
     ```
   - Activate the environment:
     ```bash
     conda activate meetingrecap
     ```

3. **Configure environment variables**:
   - Create a `.env` file at the root of the project and add your **OpenAI API Key** and **Modal Tokens**:
     ```plaintext
     OPENAI_API_KEY=your_openai_api_key
     MODAL_TOKEN_ID=your_modal_token_id_token
     MODAL_TOKEN_SECRET=your_modal_token_secret_token
     ```

4. **Run the Gradio interface**:
   - Launch the app using the command below:
     ```bash
     python app.py
     ```

---

## Usage
1. **Uploading Audio**:
   - Upload an MP3 audio file of a meeting for transcription.
   - You can also use the provided sample audio (`./assets/audios/trimmed_meeting_audio.mp3`) or any other MP3 file.

2. **Processing the Audio**:
   - The app will transcribe the audio using `Whisper` and then generate a meeting recap using `LLaMA`.

3. **Output**:
   - The generated meeting minutes include:
     - **Summary**: A concise overview of the meeting.
     - **Key Discussion Points**: Major topics discussed during the meeting.
     - **Takeaways**: Important conclusions or notes.
     - **Action Items**: Tasks with assigned owners.

4. **Logging**:
   - Every significant step (e.g., audio transcription, meeting recap generation, errors) is logged for traceability and debugging.

5. **Persistent Model Storage**:
   - Models are stored either in Google Drive or temporary runtime storage, based on your setup.

---

## Sample Audio File
- The provided sample audio file `trimmed_meeting_audio.mp3` can be used for testing. You can also upload your own MP3 audio files.

---

## Docker Deployment (Optional)
If you'd like to run the app in a Docker container, follow these steps:

1. **Build the Docker image**:
   ```bash
   docker build -t meetingrecap-app .
   ```

2. **Run the Docker container**:
   ```bash
   docker run -p 7860:7860 --env-file .env meetingrecap-app
   ```

---

### ⬅ [🔗 Back to Premium Projects](../../../README.md#-ai-and-llm-solutions)
