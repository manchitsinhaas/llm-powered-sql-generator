# Gemini SQL Query Generator with Streamlit

This project is a Natural Language to SQL (NL2SQL) web application built using Streamlit and Google Gemini Pro. It converts English questions into SQL queries and executes them on a SQLite database.

The system enables users to interact with a database using plain English without writing SQL manually.

---

## Project Overview

This application:

- Accepts user questions in natural language
- Uses Google Gemini Pro to convert the question into an SQL query
- Executes the generated SQL query on a SQLite database
- Displays the results dynamically in a Streamlit web interface

The database used in this project is:

**Database Name:** `student.db`  
**Table Name:** `STUDENT`  
**Columns:**
- NAME  
- CLASS  
- SECTION  

---

## Architecture Flow

1. User enters a question in plain English.
2. Gemini Pro converts the question into a valid SQL query.
3. The application executes the SQL query on the SQLite database.
4. Query results are displayed in the Streamlit interface.

---

## Technology Stack

**Language**
- Python 3.x  

**Framework**
- Streamlit  

**Database**
- SQLite  

**LLM Integration**
- Google Gemini Pro (google-generativeai SDK)

**Environment Management**
- python-dotenv  

---

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/gemini-sql-streamlit-app.git
cd gemini-sql-streamlit-app
```

### 2. Install Dependencies

```bash
pip install streamlit python-dotenv google-generativeai
```

### 3. Configure Environment Variables

Create a `.env` file in the root directory:

```
GOOGLE_API_KEY=your_google_api_key_here
```

Make sure your API key is valid and active.

---

## Database Setup

Ensure that the file:

```
student.db
```

exists in the root directory.

The database must contain a table:

```sql
CREATE TABLE STUDENT (
    NAME TEXT,
    CLASS TEXT,
    SECTION TEXT
);
```

You can insert sample records for testing.

---

## Running the Application

Start the Streamlit server:

```bash
streamlit run app.py
```

The application will open in your browser at:

```
http://localhost:8501
```

---

## Example Queries

You can ask questions such as:

- How many entries of records are present?
- Show all students studying in Data Science class
- List students in Section A
- Count students in Class 10

The system automatically converts these questions into SQL queries and fetches results.

---

## Key Functional Components

### 1. Gemini Response Function

- Loads Gemini Pro model
- Sends structured prompt + user question
- Returns generated SQL query

### 2. SQL Execution Function

- Connects to SQLite database
- Executes generated SQL query
- Fetches results
- Returns rows to Streamlit UI

---

## Security Considerations

This is a demonstration project. In production:

- Validate generated SQL before execution
- Prevent SQL injection risks
- Add query sanitization
- Add authentication and rate limiting
- Log and monitor generated queries

---

## Future Enhancements

- Add support for multiple tables
- Implement schema auto-detection
- Add SQL query validation layer
- Add conversational memory
- Deploy using Streamlit Cloud or Docker
- Add role-based access control

---

## Project Purpose

This project demonstrates:

- Large Language Model integration
- Prompt engineering for NL2SQL conversion
- Real-time database interaction
- Full-stack ML application deployment

It is designed for portfolio presentation and educational demonstration.

---

## License

This project is intended for educational and demonstration purposes.
