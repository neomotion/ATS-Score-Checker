# ATS-Score-Checker

This project is an ATS (Applicant Tracking System) Score Checker built using Streamlit and Google Gemini AI, designed to evaluate CVs and job descriptions. It ranks CVs based on relevance to the job description, section-by-section, with an overall relevancy score for each CV.

**Table of Contents:**

  Features
  Setup and Installation
  Running the Application
  Key Hyperparameters
  Using the Model
  Ranking CV Sections
  Overall CV Ranking

**Features**
**ATS Score Calculation:** Evaluate CVs against job descriptions to produce a detailed ATS score.
**Section Ranking:** Ranks individual CV sections (e.g., Work Experience, Education, Skills) based on relevance to the job description.
**Overall CV Ranking:** Ranks multiple CVs by relevancy score, giving preference to the best-suited profiles for the position.

**Setup and Installation**

**1. Dependencies**

The project requires the following dependencies:

  streamlit
  
  PyPDF2
  
  dotenv
  
  google.generativeai
  

**2. Installation Instructions**

Clone the Repository:

  git clone <repository-url>
  cd <repository-directory>

Create a Virtual Environment:

  python -m venv env
  source env/bin/activate   # On macOS/Linux
  env\Scripts\activate      # On Windows

Install Dependencies:

  pip install -r requirements.txt

Environment Setup: Create a .env file in the project root directory and add your Google Gemini API key:

  GOOGLE_GEMINI_KEY=<your_google_gemini_api_key>

Run Streamlit:
To run the application locally, ensure your virtual environment is active, and then execute:

  streamlit run ats_score_checker.py

**Key Hyperparameters**
The model is fine-tuned to evaluate CV relevance based on these key parameters:

Relevance Score Threshold: A scoring scale between 0 and 1, with higher scores indicating a closer match.

**Section Weighting:**

  Skills Match: Prioritizes matching job description keywords in the "Skills" section.
  
  Experience Match: Emphasizes domain-specific experience and role tenure.
  
  Education Match: Prefers degree relevance to the job requirements.
  
  Soft Skills Match: Scores for communication, teamwork, and leadership where applicable.
  
  These parameters ensure the model effectively prioritizes CVs that closely match the job description, optimizing candidate recommendations.
  
  
**Using the Model**
Ranking CV Sections

To rank individual sections in a CV:

  Upload Resume and Paste Job Description: Use the Streamlit interface to upload a CV in PDF format and paste a relevant job description.
  
  Section Relevance: The model evaluates each CV section (e.g., Skills, Work Experience) against the job description, identifying the sections most aligned with role requirements.
  
  Section Scores: Each section receives a relevancy score between 0 and 1. Sections with higher scores indicate a stronger match.
  
  Overall CV Ranking
      
   To rank multiple CVs:
    
   Multiple CV Input: The system accepts multiple CVs along with a single job description.
      
   Relevancy Factors:
      
   Skills: Includes tools, languages, and expertise levels in alignment with the job description.
        
   Experience: Measures years in role, relevant industries, and key achievements.
        
   Education: Prioritizes degrees, certifications, and any field-specific qualifications.
        
   Soft Skills: Weights attributes like communication and teamwork where relevant.
        
   Output: The model provides a ranked list of CVs based on total relevancy, with explanations for the ranking. The highest-ranked CV is most suitable for the job description provided.
        
      
**License**

This project is licensed under the MIT License.

