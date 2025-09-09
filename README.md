# Note2Text: Image & Handwriting to Smart Survey

A FastAPI-based backend for processing handwritten or printed note images. The API extracts text, generates questions, categorizes notes, suggests related notes, and checks for violent content using OpenAI GPT models.

## Features

- Extracts text from uploaded note images (OCR via OpenAI)
- Generates survey questions from extracted text
- Categorizes notes (Education, Health, Finance, etc.)
- Suggests related note titles
- Detects violent content in notes

## Project Structure

```
app/
  main.py
  routes/
    note_routes.py
  services/
    ocr_service.py
    question_service.py
    category_service.py
    related_service.py
    violence_service.py
  utils/
    image_utils.py
.env
requirements.txt
```

## Setup

1. **Download the zip file**

2. **Install dependencies**
   ```sh
   pip install -r requirements.txt
   ```

3. **Set up environment variables**

   Create a `.env` file in the root directory with your OpenAI API key:
   ```
   OPENAI_API_KEY="your-openai-api-key"
   ```

4. **Run the server**
   ```sh
   uvicorn app.main:app --reload
   ```

## API Usage

### `POST /notes/process`

Upload an image file to process a note.

**Request:**
- `file`: image file (form-data)

**Response:**
```json
{
  "extracted_text": "...",
  "generated_questions": "...",
  "category": "...",
  "related_notes": "...",
  "violence_check": "..."
}
```
<img width="1600" height="651" alt="image" src="https://github.com/user-attachments/assets/4895ac0d-6f04-49c5-9eb5-c906ba988729" />

