# 🤖 Natural Language to SQL Agent using IBM Watsonx.ai and LangChain

This project allows users to interact with a SQL database using **natural language**. It uses **IBM Watsonx's Granite-3-2-8B Instruct LLM** integrated with **LangChain** to dynamically generate SQL queries and fetch results from a **MySQL database**.

> 🔍 Ask questions like:
> - "What is the total revenue by genre?"
> - "List all albums by 'AC/DC'"
> - "How many customers are from Canada?"



## 🧠 Key Features

- ✅ Converts plain English to SQL queries
- ✅ Uses IBM Watsonx's LLM (Granite 3-2-8B Instruct) via `WatsonxLLM`
- ✅ Executes queries securely on a MySQL database
- ✅ Handles SQL parsing errors and ensures verbose output
- ✅ Command-line interface with `--prompt` argument


## 🛠️ Technologies Used

- 🧠 **IBM Watsonx.ai Granite-3-2-8B Instruct**
- 🧱 **LangChain**
- 🐬 **MySQL** with **Chinook Sample Database**
- 🐍 **Python**
- 🔐 **argparse** for command-line usage


## 📁 Project Structure

```
project/
│
├── llm_agent.py        # Test script to invoke LLM only
├── sql_agent.py        # Main agent script that handles user queries
├── README.md           # Project documentation
```


## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/aaradhya466/NLQ-to-SQL-Agent-IBM-Watsonx.git
cd NLQ-to-SQL-Agent-IBM-Watsonx
```

### 2. Install Required Packages

```bash
pip install ibm-watsonx-ai langchain mysql-connector-python sqlalchemy
```

> 💡 You may also need:  
> `pip install argparse` (in case it's not pre-installed)

### 3. Setup IBM Watsonx Credentials

Ensure you have access to IBM Watsonx.ai and replace the following inside `sql_agent.py` and `llm_agent.py`:

```python
credentials = {
    "url": "https://us-south.ml.cloud.ibm.com"
}
project_id = "skills-network"
```

> ✅ You may also need to include `apikey` if required for your Watsonx instance.

### 4. Update MySQL Configuration

Replace the following lines with your own MySQL credentials in `sql_agent.py`:

```python
mysql_username = 'your_username'
mysql_password = 'your_password'
mysql_host = 'your_host_or_ip'
mysql_port = '3306'
database_name = 'Chinook'
```

Ensure the MySQL server is running and the Chinook sample DB is imported.

---

## 🚀 How to Run

### 🔹 Option 1: Invoke LLM Only

```bash
python llm_agent.py
```

### 🔹 Option 2: Query Database Using Natural Language

```bash
python sql_agent.py --prompt "Show top 5 customers by total purchase"
```

---

## 🧪 Sample Prompts to Try

- `"List all tracks longer than 5 minutes"`
- `"Find total sales by country"`
- `"Get names of all customers in France"`
- `"Show the names of employees and their job titles"`

---

## 📌 Notes

- The project uses `ZERO_SHOT_REACT_DESCRIPTION` agent type from LangChain for SQL reasoning.
- Agent handles parsing errors and logs verbose output for debugging.
- The Chinook database must be running on the specified host and port.

---

## 👤 Author

**Aaradhya**  
2nd Year BCA Student | Specialization in AI & Data Science  
📧 Email: aaradhya8200@gmail.com  
🌐 GitHub: [@aaradhya466](https://github.com/aaradhya466)

---

## 🎯 Future Improvements

- Add frontend interface to interact with the agent
- Integrate with other SQL dialects (e.g., PostgreSQL, SQLite)
- Secure credential management via `.env` or vaults
```
