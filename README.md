# AI-Resume-
# Resume Editor Setup Guide

This guide will help you set up both the React frontend and FastAPI backend for the Resume Editor application.

## Project Structure

```
resume-editor/
├── frontend/          # React application
├── backend/           # FastAPI application
├── requirements.txt   # Python dependencies
└── README.md         # This file
```

## Backend Setup (FastAPI)

### 1. Create Backend Directory and Files

```bash
mkdir resume-editor
cd resume-editor
mkdir backend
cd backend
```

### 2. Create Python Virtual Environment

```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies

Create a `requirements.txt` file with the provided dependencies and install:

```bash
pip install -r requirements.txt
```

### 4. Create the FastAPI Application

Save the FastAPI backend code as `main.py` in the backend directory.

### 5. Run the Backend Server

```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

The backend will be available at: `http://localhost:8000`

API documentation will be available at: `http://localhost:8000/docs`

## Frontend Setup (React)

### 1. Create React Application

```bash
# From the project root directory
npx create-react-app frontend
cd frontend
```

### 2. Install Additional Dependencies

```bash
npm install lucide-react
```

### 3. Replace App.js

Replace the contents of `src/App.js` with the provided React component code.

### 4. Update App.css (Optional)

Add any additional styling if needed.

### 5. Start the Frontend Development Server

```bash
npm start
```

The frontend will be available at: `http://localhost:3000`

## Features

### Core Functionality
- ✅ Upload resume files (PDF, DOC, DOCX)
- ✅ Edit personal information (name, email, phone)
- ✅ Edit professional summary
- ✅ Add/edit/remove work experience entries
- ✅ Add/edit/remove education entries
- ✅ Add/edit/remove skills
- ✅ Save and load resumes
- ✅ Preview resume
- ✅ Download resume as PDF

### AI Enhancement
- ✅ Enhance professional summary with AI
- ✅ Enhance job descriptions with AI
- ✅ Enhance education descriptions with AI
- ✅ Mock AI backend with realistic enhancements

### API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/upload-resume` | Upload and parse resume file |
| POST | `/enhance-section` | Enhance section with AI |
| POST | `/resumes` | Create new resume |
| GET | `/resumes` | Get all saved resumes |
| GET | `/resumes/{id}` | Get specific resume |
| PUT | `/resumes/{id}` | Update existing resume |
| DELETE | `/resumes/{id}` | Delete resume |
| POST | `/download-resume` | Generate and download PDF |
| GET | `/health` | Health check |

## Usage Instructions

### 1. Upload Resume
- Click "Upload Resume" button
- Select a PDF, DOC, or DOCX file
- The system will parse and populate the form fields

### 2. Edit Resume Sections
- Fill in personal information
- Add professional summary
- Add work experience entries
- Add education entries
- Add skills

### 3. Enhance with AI
- Click "Enhance with AI" next to any section
- The system will improve the content using mock AI
- Review and edit the enhanced content as needed

### 4. Save Resume
- Click "Save" to store the resume in the backend
- Saved resumes appear as buttons in the header
- Click on saved resume buttons to load them

### 5. Preview and Download
- Click "Preview" to see the formatted resume
- Click "Download PDF" to generate and download a PDF version

## Development Notes

### Mock AI Implementation
The current implementation uses a mock AI service that adds predefined enhancements. To integrate with real AI services:

1. Replace `MockAIEnhancer` class with actual AI service calls
2. Consider using OpenAI GPT, Google Gemini, or other LLM APIs
3. Add proper API key management and environment variables

### File Upload Processing
The current resume parsing is mocked. For production:

1. Implement actual PDF parsing using `pdfplumber` or `PyPDF2`
2. Implement Word document parsing using `python-docx`
3. Add NLP processing using `spaCy` or `NLTK` for content extraction
4. Add error handling for various file formats and structures

### Database Integration
Current implementation uses in-memory storage. For production:

1. Integrate with PostgreSQL, MongoDB, or other databases
2. Add proper data models and migrations
3. Implement user authentication and authorization
4. Add data validation and sanitization

### Security Considerations
For production deployment:

1. Add authentication and authorization
2. Implement file upload security (virus scanning, size limits)
3. Add rate limiting for AI enhancement requests
4. Use HTTPS for all communications
5. Add input validation and sanitization
6. Implement proper error handling and logging

## Troubleshooting

### Backend Issues
- **Port already in use**: Change the port in the uvicorn command
- **Module not found**: Ensure virtual environment is activated and dependencies are installed
- **CORS errors**: Check that frontend URL is in the CORS allowed origins

### Frontend Issues
- **API connection failed**: Ensure backend is running on port 8000
- **Upload not working**: Check file size limits and supported formats
- **Enhancement not working**: Check backend logs for AI service errors

### Common Problems
- **File permissions**: Ensure the application has write permissions for temp directory
- **Memory issues**: Large files may cause memory problems with current implementation
- **PDF generation fails**: Check that reportlab is properly installed

## Next Steps for Production

1. **User Authentication**: Add user registration, login, and session management
2. **Real AI Integration**: Replace mock AI with actual AI services
3. **Database**: Implement persistent storage with proper database
4. **File Storage**: Use cloud storage (AWS S3, Google Cloud) for file uploads
5. **Caching**: Add Redis or similar for performance optimization
6. **Monitoring**: Add logging, metrics, and error tracking
7. **Testing**: Add comprehensive unit and integration tests
8. **Deployment**: Containerize with Docker and deploy to cloud platforms

## License

This project is for educational purposes. Please ensure you have proper licenses for any AI services or libraries used in production.


