# 🎥 Gemini-Powered YouTube Summarizer

A web-based application that leverages the power of Google's Gemini AI to generate comprehensive, well-formatted summaries of any YouTube video instantly. 

Built with a lightweight Python Flask backend and a modern, responsive frontend, this project is fully containerized and ready for deployment on Google Cloud Run.

## ✨ Features

- **Instant AI Summarization:** Extracts and condenses key information from YouTube videos using the Gemini 2.5 Flash model.
- **Custom Instructions:** Allows users to pass custom prompts (e.g., "Explain like I'm 5", "Summarize in 3 bullet points") to tailor the output.
- **Modern UI/UX:** A clean, single-page application built with modern CSS, featuring loading states, interactive buttons, and a polished result display.
- **Rich Text Formatting:** Integrates `Marked.js` to automatically convert Gemini's Markdown responses into beautifully formatted HTML (bold text, bullet points, headers).
- **Secure Setup:** Uses environment variables to protect Google Cloud Project IDs during local development.
- **Serverless Deployment:** Configured for seamless deployment to Google Cloud Run.

## 🛠️ Tech Stack

- **Backend:** Python, Flask
- **AI Integration:** Google GenAI SDK (`google-genai`), Vertex AI
- **Frontend:** HTML5, CSS3, Vanilla JavaScript, Marked.js
- **Deployment:** Google Cloud Run, Google Cloud CLI

## 🚀 Local Development Setup

### Prerequisites

1. **Python 3.8+** installed on your machine.
2. **Google Cloud CLI** (`gcloud`) installed and configured.
3. A Google Cloud Project with the **Vertex AI API** enabled and billing configured.

### 1. Clone the Repository

```bash
git clone https://github.com/Htet-Khant-Linn/gemini-powered-youtube-summarizer.git
```

### 2. Set Up the Virtual Environment

Create and activate an isolated Python environment:

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Mac/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the root directory and add your Google Cloud Project ID:

```env
GOOGLE_CLOUD_PROJECT=your-google-cloud-project-id
```

### 5. Authenticate with Google Cloud

To allow your local code to securely communicate with Vertex AI, generate Application Default Credentials (ADC):

```bash
gcloud auth application-default login
gcloud auth application-default set-quota-project your-google-cloud-project-id
```

### 6. Run the Application

Start the Flask development server:

```bash
python app.py
```

Navigate to `http://localhost:8080` in your web browser to test the application!

## ☁️ Deployment to Google Cloud Run

Deploying this application to the internet is completely serverless and takes just one command.

Ensure you are authenticated and your CLI is pointing to the correct project:

```bash
gcloud config set project your-google-cloud-project-id
```

Run the deployment command from the root directory:

```bash
gcloud run deploy --source .
```

Follow the interactive prompts:

- **Service Name:** Press Enter to accept the default.
- **Region:** Select your preferred region (e.g., `us-central1`).
- **Allow unauthenticated invocations:** Type `y` to make the site public.

Once complete, the CLI will output your live, secure `https://` URL!

## 📁 Project Structure

```
├── templates/
│   └── index.html         # Frontend UI, CSS, and Client-side JavaScript
├── .env                   # Environment variables (ignored in version control)
├── .gitignore             # Files to ignore in Git (includes .env and venv)
├── app.py                 # Flask server and Gemini API integration
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
```

## 👨‍💻 Author

**Htet Khant Linn**

Feel free to reach out or contribute to this repository!
