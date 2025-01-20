```markdown
# SQL Agent with LangChain and PostgreSQL

This project demonstrates how to use **LangChain**, **OpenAI**, and **SQLAlchemy** to interact with a PostgreSQL database, execute SQL queries, and utilize a React-like agent to process user queries in natural language. The code connects to a PostgreSQL database, creates tools for database interaction, and leverages a Large Language Model (LLM) to analyze and respond to user queries about the database.

## Features

- **PostgreSQL Database Connection**:
  - Connects to a local PostgreSQL database using SQLAlchemy.
  - Runs queries to retrieve metadata and records from the database.
- **LangChain Integration**:
  - Uses the `langchain_community` package to create tools for SQL query execution.
  - Implements a React-like agent that interacts with the database via natural language prompts.
- **OpenAI LLM**:
  - Leverages OpenAI's GPT model to interpret and execute user queries on the database.
- **Dynamic Prompting**:
  - Uses a system prompt template for formatting and optimizing queries for SQL dialects.
- **Streaming Outputs**:
  - Streams query responses dynamically for real-time interaction.

## Prerequisites

- Python 3.8 or higher
- PostgreSQL database running locally
- Required Python libraries:
  - `langchain`
  - `langchain_community`
  - `openai`
  - `psycopg2`
  - `sqlalchemy`

## Setup Instructions

1. Clone the repository or copy the script to your local machine.
2. Install the required Python dependencies:
   ```bash
   pip install langchain langchain_community openai psycopg2 sqlalchemy
   ```
3. Ensure your PostgreSQL database is running locally and accessible.
4. Update the database connection details in the `get_engine_for_postgresql_db` function:
   ```python
   db_user = "your_username"
   db_password = "your_password"
   db_host = "localhost"
   db_port = "5432"
   db_name = "your_database"
   ```

## Usage

1. **Run the Script**:
   Execute the script to establish the database connection and load the agent.
   ```bash
   python your_script_name.py
   ```
2. **Query the Database**:
   The example query included in the script:
   ```python
   example_query = "which employee has the minimum salary?"
   ```
   The agent streams the output dynamically based on the query.

## Code Walkthrough

### Database Connection
The `get_engine_for_postgresql_db` function creates an SQLAlchemy engine to connect to the PostgreSQL database.

### LangChain Integration
- `SQLDatabaseToolkit` is used to create tools for interacting with the database.
- A system prompt template is pulled from LangChain Hub to guide the query processing.

### LLM and Agent
- The agent is initialized using `create_react_agent`, which combines the LLM with the database tools.
- The `example_query` demonstrates querying the database using natural language.

## Example Output

When querying:
```text
Which employee has the minimum salary?
```
The agent dynamically processes the query, runs the appropriate SQL, and returns the result.

## Troubleshooting

- If the database connection fails, verify the credentials and database accessibility.
- Ensure all required libraries are installed.
- Check that the OpenAI API key is valid and set as an environment variable.

## Contributing

Feel free to fork this repository, make changes, and submit pull requests. Contributions to improve the functionality or documentation are welcome.

## License

This project is licensed under the MIT License.
```

You can paste this markdown content directly into your `README.md` file.
