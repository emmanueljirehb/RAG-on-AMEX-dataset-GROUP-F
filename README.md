# 🧠 RAG-Powered SQL QA System using XAAMP & LangChain " AMEX " Dataset


![ChatGPT Image Jul 10, 2025, 02_51_10 PM](https://github.com/user-attachments/assets/fc1f304e-b718-46df-802f-33f5fb8425d6)

A Retrieval-Augmented Generation (RAG) pipeline that lets users ask **natural language questions** and receive **AI-generated answers** derived from structured **SQL data** — all powered by **LangChain**, **XAAMP**, and the **American Express Campus Challenge Dataset** from Kaggle.

---

## 📂 Dataset
**Source:** [American Express Campus Challenge Dataset](https://www.kaggle.com/datasets/pratsharma7/the-american-express-campus-challenge-dataset)

- 🏦 Real-world financial dataset
- 📊 Customer transactions and demographics
- 📁 Format: CSV → Imported into XAAMP MySQL

---

## 🧱 Tech Stack

| Tool | Role |
|------|------|
| 🧠 **LangChain** | Converts natural language to SQL queries using LLM |
| 🗃️ **XAAMP Server** | Hosts the MySQL database locally |
| 🐍 **PyMySQL** | Connects Python with XAAMP MySQL |
| 🔎 **FAISS (optional)** | Enables semantic retrieval for text chunks |
| 🤖 **OpenAI LLM** | Powers the conversational interface |

---

## 🔄 Workflow

### 1️⃣ Dataset Setup
- Downloaded Kaggle dataset
- Cleaned and formatted for SQL
- Loaded into XAAMP's MySQL via **phpMyAdmin**

### 2️⃣ XAAMP Configuration
- Started `Apache` & `MySQL` from XAAMP Control Panel
- Created a new DB `amex_data`
- Imported the dataset as a table

### 3️⃣ Python ↔ SQL Connection
- Used `PyMySQL` to connect to the XAAMP MySQL DB

```python
import pymysql
conn = pymysql.connect(host="localhost", user="root", password="", database="amex_data")
```


### 4️⃣ LangChain Integration

We set up a robust connection using LangChain's SQL capabilities:

  * **SQLDatabase with LangChain**: Established a connection to our MySQL database.
  * **SQLDatabaseChain for NL Queries**: Created a `SQLDatabaseChain` to seamlessly parse and execute natural language (NL) queries.

<!-- end list -->

```python
from langchain.chains import SQLDatabaseChain
from langchain.sql_database import SQLDatabase
from langchain.chat_models import ChatOpenAI

# Setup database connection (assuming XAMPP MySQL running on localhost)
db = SQLDatabase.from_uri("mysql+pymysql://root:@localhost/amex_data")

# Initialize the LangChain SQLDatabaseChain with a ChatOpenAI LLM
db_chain = SQLDatabaseChain(llm=ChatOpenAI(), database=db)
```

-----

### 5️⃣ Ask Me Anything\! 💬

Experience real-time question-answering with Large Language Models (LLMs)\!

**Example Query:**

```python
query = "What are the top spending categories?"
response = db_chain.run(query)
# The 'response' variable will contain the answer in natural language.
```

-----

## 📌 Features

✅ **Local SQL Database**: Utilizes **XAAMP MySQL** for a local and accessible database environment.
✅ **Real-time Question-Answering**: Powered by **LLMs** for instant, natural language responses.
✅ **Plug-and-Play**: Designed for **any tabular dataset**, offering high adaptability.
✅ **Optional Enhancement**: Capability to add **FAISS for semantic search** of text metadata, extending search capabilities.

-----

## 🎯 Ideal For

  * **Data Science & NLP Portfolio Projects** 📈
  * **Financial Data Analytics** with LLMs 💰
  * **Demonstrating LangChain + SQL Integration** 🔗
  * **RAG-based Research Workflows** (Retrieval-Augmented Generation) 📚

-----

## 📷 Project Architecture

A clear flow from user query to data insights:

```
🧑‍💻 User Query (Natural Language)
        ↓
  LangChain + OpenAI (LLM)
        ↓
SQLDatabaseChain → Generates SQL Query
        ↓
 XAAMP MySQL → Executes SQL Query
        ↓
📊 Result → Returned in Natural Language
```

-----

## 🚀 Empowering SQL with Language Models: Bridging Data & Decision-Making 🧠

This project demonstrates a powerful integration of LangChain with a local SQL database, enabling real-time natural language querying for tabular datasets.

-----


-----

## 📬 Connect With Me

Like the project? Let’s connect\!

  * 🔗 [GitHub](https://github.com/emmanueljirehb) 
  * 📊 [Kaggle](https://www.kaggle.com/emmanueljireh)
  * 📝 [Medium](https://medium.com/@emmanueljirehb)
  * 💼 [LinkedIn](https://www.linkedin.com/in/emmanueljirehb)

-----
