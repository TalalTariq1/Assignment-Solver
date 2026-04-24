# AI Assignment Solver (Backend)

A high-performance FastAPI microservice that processes assignment documents using Llama-3.3-70B (via Groq) and generates formatted Word documents.

## 🛠️ Core Technology Stack

- **Framework:** FastAPI (Python)
- **AI Integration:** Groq API (Llama-3.3-70b-versatile)
- **Document Processing:** python-docx
- **Server:** Gunicorn with Uvicorn Workers
- **Deployment:** Railway

## 📡 API Endpoints

### 1. Upload & Process
`POST /upload`
- **Purpose:** Accepts a `.docx` file and student metadata, sends content to Groq, and generates a solved document.
- **Form Data:**
    - `file`: Assignment File (.docx)
    - `name`, `roll_number`, `section`, `subject`: Student details
    - `language`: Target programming language (e.g., Python, C++, Java)

### 2. Download Result
`GET /download/{filename}`
- **Purpose:** Serves the generated `.docx` file to the frontend for user download.

## ⚙️ Environment Variables

The following variables must be configured in the Railway dashboard:

| Variable | Description |
| :--- | :--- |
| `GROQ_API_KEY` | Secret API key from Groq Cloud |
| `PORT` | Set to `8080` |

## 🏗️ Local Setup

1. **Clone the repo:**
   ```bash
   git clone [your-private-repo-link]
   cd assignment-backend

   Install dependencies:

2.**Install dependencies:**
Bash
pip install -r requirements.txt
3. **Run the server:**

Bash
uvicorn main:app --reload
🔒 Security Note
This repository is kept private to protect API credentials and proprietary document-parsing logic. All sensitive keys are managed via secure Environment Variables.

📝 License
MIT License
