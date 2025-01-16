# Smart Applicant Tracking System (SATS)

SATS is an advanced applicant tracking system designed to revolutionize the recruitment process. Unlike traditional systems that rely solely on string matching, SATS harnesses the power of contextual understanding. By analyzing job descriptions and candidate resumes comprehensively, SATS evaluates candidates based on factors such as educational background, work experience, and domain expertise, providing a more accurate and nuanced assessment. 
---

## Features

### 1. **Resume Evaluation**
- Upload a PDF resume and a job description.
- Extracts text from the PDF and compares it with the job description.
- Provides a structured response including:
  - **Job Description Match Percentage**
  - **Missing Keywords**
  - **Profile Summary**

### 2. **Bulk Resume Evaluation**
- Upload multiple PDF resumes for simultaneous evaluation.
- Generates a leaderboard ranking resumes by their job description match score.

### 3. **User Authentication**
- Includes endpoints for user registration, login, and logout.
- Tracks logged-in users using session management.

### 4. **Error Handling**
- Handles invalid files, text extraction issues, and missing input data gracefully.

---

## Technology Stack

### Backend
- **Python**: Core programming language.
- **Flask**: Lightweight framework for building the API.
- **PyPDF2**: Library for extracting text from PDF files.

### AI and NLP
- **Google Generative AI**: Used for contextual analysis of resumes and job descriptions.
- **dotenv**: Manages environment variables securely.

### Utilities
- **Werkzeug**: Ensures secure handling of uploaded filenames.
- **Logging**: Debugging and tracking application activity.

### Deployment and Security
- **Environment Variables**: API keys and secrets are securely stored using `.env` files.

---

## Installation

### Prerequisites
- Python 3.8+
- Google API Key with access to Generative AI services.

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/resume-evaluation.git
   cd resume-evaluation
   ```
2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Set up environment variables:
   - Create a `.env` file in the root directory.
   - Add the following line:
     ```
     GOOGLE_API_KEY=your_google_api_key
     ```
5. Run the application:
   ```bash
   python app.py
   ```
6. Access the app at `http://127.0.0.1:5000`.

---

## API Endpoints

### 1. **Evaluate Resume**
- **Endpoint**: `/evaluate_resume`
- **Method**: POST
- **Parameters**:
  - `file`: PDF resume (required)
  - `job_description`: Job description text (required)
- **Response**:
  ```json
  {
    "JD Match": "75%",
    "MissingKeywords": ["Python", "Data Analysis"],
    "Profile Summary": "Experienced data scientist with expertise in big data and analytics."
  }
  ```

### 2. **Evaluate Bulk Resumes**
- **Endpoint**: `/evaluate_bulk_resumes`
- **Method**: POST
- **Parameters**:
  - `files`: List of PDF resumes (required)
  - `job_description`: Job description text (required)
- **Response**:
  ```json
  [
    {
      "filename": "resume1.pdf",
      "match_score": 85.0,
      "response": { ... }
    },
    {
      "filename": "resume2.pdf",
      "match_score": 78.0,
      "response": { ... }
    }
  ]
  ```

### 3. **User Sign-Up**
- **Endpoint**: `/signup`
- **Method**: POST
- **Parameters**:
  - `email`: User email (required)
  - `username`: User name (required)
  - `password`: Password (required)
- **Response**:
  ```json
  { "message": "User created successfully" }
  ```

### 4. **User Login**
- **Endpoint**: `/login`
- **Method**: POST
- **Parameters**:
  - `email`: User email (required)
  - `password`: Password (required)
- **Response**:
  ```json
  { "message": "Logged in successfully" }
  ```

### 5. **User Logout**
- **Endpoint**: `/logout`
- **Method**: POST
- **Response**:
  ```json
  { "message": "Logged out successfully" }
  ```

---

## Future Enhancements
- **Database Integration**: Replace in-memory storage with a database for user data and resume records.
- **Enhanced AI Feedback**: Provide detailed improvement suggestions for resumes.
- **Asynchronous Processing**: Optimize bulk resume evaluation for large datasets.
- **Frontend Interface**: Build a web-based UI for easier interaction with the system.

---

## Key Features

- **Contextual Analysis:** Utilizes advanced algorithms to understand job descriptions and resumes in context.
- **Comprehensive Evaluation:** Considers multiple factors including education, experience, and skills for candidate assessment.
- **Leaderboard System:** Implements a leaderboard to rank candidates based on match scores, facilitating efficient recruitment by highlighting top matches.

Join us in shaping the future of recruitment with SATS!

## Contributing

Contributions are welcome! If you find any issues or have suggestions, please open an issue or submit a pull request.

## Team Members
- **Shubham Bhimsaria**
- **Satyesh Das**
- **Shrey Pant**

## License

This project is licensed under the [MIT License](LICENSE).
