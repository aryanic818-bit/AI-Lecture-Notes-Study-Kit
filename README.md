# AI-Lecture-Notes-Study-Kit# 📚 Lecture Notes → Study Kit

Upload a lecture PDF or PowerPoint and get:

- a **summary** with key points
- a **10-question multiple-choice quiz** with answers, explanations and a score
- **flashcards** (5–20, your choice)
- a downloadable **Markdown study kit**

Built with [Streamlit](https://streamlit.io) and Google's Gemini Flash model (`gemini-3.5-flash`).

## Files

| File | Purpose |
|------|---------|
| `app.py` | The Streamlit app |
| `requirements.txt` | Python dependencies |
| `README.md` | This guide |

## Run locally

1. Install Python 3.9+ and get a free API key from [Google AI Studio](https://aistudio.google.com/app/apikey).
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Set your key (or paste it into the app's sidebar):
   - Mac/Linux: `export GEMINI_API_KEY="your-key"`
   - Windows (PowerShell): `$env:GEMINI_API_KEY="your-key"`
4. Start the app:
   ```bash
   streamlit run app.py
   ```

## Put it on GitHub

1. Create a free account at [github.com](https://github.com) and click **New repository** (e.g. `study-kit-app`, set to **Public**; do not add any files).
2. Create a `.gitignore` file in your project folder containing these two lines, so your key is never uploaded:
   ```
   .streamlit/secrets.toml
   __pycache__/
   ```
3. In your project folder, run:
   ```bash
   git init
   git add app.py requirements.txt README.md .gitignore
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/study-kit-app.git
   git push -u origin main
   ```
   (No Git? On GitHub choose **Add file → Upload files** and drag in the files.)

## Deploy on Streamlit Community Cloud

1. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub.
2. Click **Create app**, choose your repository, branch `main`, and main file `app.py`.
3. Open **Advanced settings → Secrets** and paste:
   ```toml
   GEMINI_API_KEY = "your-key"
   ```
4. Click **Deploy**. In a minute or two you get a public link to share.

## Notes and limits

- Only text-based PDFs/PPTX work. Scanned PDFs (images of pages) have no text to read.
- Very long files are cut to the first 60,000 characters.
- The model name can be changed in the sidebar if Google releases a newer Flash model.
- Always check AI-generated answers against your original notes.
