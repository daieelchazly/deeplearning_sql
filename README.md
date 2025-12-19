# deeplearning_sql
Voice-to-SQL Assistant Demo Points

Objective
Convert natural voice questions about a database (Northwind) into executable SQL (selecting, joining, inserting ansd more)queries automatically.

Database Setup
Uses Northwind CSV files: Employees, Customers, Orders, OrderDetails, Products, Categories, Shippers.
CSVs are loaded, cleaned, and stored in SQLite.
Cleaning includes stripping whitespace and removing control characters and others

Key Features
Voice input processed via OpenAI Whisper model (base).
SQL generation using GPT-4o-mini and adding schema rules for more guidness.
Avoids inventing values or column names.
Shows results or rows affected for updates.
Errors handled gracefully.

Execution Flow
User speaks a question into the Gradio interface.
Whisper transcribes audio → text.
GPT generates one valid SQL statement based on schema and user question.
SQL executed against SQLite DB

Gradio Interface
Audio input for question.
Text output showing question, generated SQL, and result.
Option to download updated CSV.

Demo Example:
“List all employees in Germany.” → SQL selects relevant records.
Tech Stack & Models
Python 3.10+
Libraries & Versions:
gradio ~3.48.0
pandas ~2.1.0
sqlite3 
whisper ~2023.12
openai ~1.36.0
torch ~2.2.0
regex

Models Used:
Whisper base – for audio transcription.
GPT-4o-mini – for SQL generation.

How to Run the Code
Install dependencies (in Colab or local environment):
Place Northwind CSV files
Set OpenAI API key in the code 
Run the Python script
Gradio interface will launch:
Speak your question.
View generated SQL and table results
