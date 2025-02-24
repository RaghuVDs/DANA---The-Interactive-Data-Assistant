# Dana: The Interactive Data Assistant

## Project Description
Dana is an interactive data assistant designed to help you analyze your data through natural language conversations. Simply upload your data files or connect to your database, and start asking questions! Dana leverages the power of Large Language Models (LLMs) and function calling to understand your requests, generate and execute SQL queries, create insightful visualizations, and provide you with data-driven answers and summaries.

## Key Features

- **Database Connectivity:** Connect to in-memory DuckDB databases for quick analysis or external PostgreSQL databases for larger datasets.
- **Data Loading:** Easily load data from CSV and Excel (XLSX, XLS) files.
- **Natural Language to SQL:** Ask questions about your data in plain English and Dana will translate them into SQL queries.
- **SQL Query Execution:** Dana automatically executes generated SQL queries against your connected database.
- **Intelligent Data Visualization:** Request visualizations like histograms, bar charts, scatter plots, line graphs, box plots, and pie charts to understand data distributions and relationships.
- **Correlation Analysis:** Quickly identify and visualize correlations between numeric columns within your datasets.
- **Summary Statistics Generation:** Obtain comprehensive summary statistics (count, mean, standard deviation, min, max, percentiles, unique values, top values, null counts & percentages) for your data columns.
- **Conversational Interface:** Interact with your data through a chat-like interface, maintaining conversation history for contextual understanding.
- **Basic Memory:** Dana remembers key insights and preferences from your conversation to provide a more personalized and efficient experience over time.
- **Response Length Control:** Choose between concise and more detailed responses from Dana.

## Getting Started

### Prerequisites
- Python 3.7+
- pip (Python package installer)
- OpenAI API Key: You will need an OpenAI API key to use the LLM functionalities. You can obtain one from OpenAI's website.

### Installation

1. Clone the repository (if you have the code in a repository, otherwise just navigate to the directory where you have the Python file).
2. Install required Python packages:

   ```bash
   pip install streamlit openai duckdb pandas plotly sqlalchemy
   ```

3. Set up OpenAI API Key:
   - Create a `.streamlit` directory in the same directory as your Python script if it doesn't exist.
   - Inside the `.streamlit` directory, create a file named `secrets.toml`.
   - Add your OpenAI API key to `secrets.toml` as follows:

   ```toml
   openai_key = "YOUR_OPENAI_API_KEY_HERE"
   ```

   Replace `YOUR_OPENAI_API_KEY_HERE` with your actual OpenAI API key.

### Running Dana

1. Navigate to the directory containing your Python script in your terminal.
2. Run the Streamlit application using the command:

   ```bash
   streamlit run your_script_name.py  # Replace your_script_name.py with the actual name of your Python file.
   ```

   Streamlit will open Dana in your web browser (usually at http://localhost:8501).

## Usage

### Connect to a Database:

- **DuckDB (In-memory):** Choose DuckDB for a quick start and in-memory database. No further configuration is needed after selecting DuckDB in the application.
- **PostgreSQL:** Select PostgreSQL and provide the required connection details (Host, Port, Database Name, User, Password) to connect to your existing PostgreSQL database.

### Load Data:

- **Upload File:** Use the file upload widget in the application to upload CSV or Excel files. Dana will automatically load the data into the connected database.

### Start Chatting:

Use the chat input box to ask questions about your data in natural language. Examples:

- "What are the average sales per region?"
- "Show me a bar chart of product categories and their total revenue."
- "Analyze the correlation between age and income."
- "Give me summary statistics for all columns in the sales table."
- "What are the top 5 selling products?"
- "Visualize the distribution of customer ages as a histogram."

### View Responses:

- Dana will respond with text answers, SQL queries used, tabular data, or visualizations based on your questions.
- Visualizations will be displayed directly in the application.
- SQL queries and tabular data will be presented in a readable format.

## Limitations and Future Enhancements

Dana is under active development, and here are some known limitations and planned future enhancements:

- **Basic Memory System:** The current memory functionality is rudimentary. Future versions will incorporate more advanced memory management for better context retention and personalized interactions.
- **Visualization Customization:** Visualization options are currently limited to default settings. Future updates will allow users to customize chart types, colors, labels, and other visual aspects.
- **Large Dataset Performance:** Performance with extremely large datasets might be constrained, especially with in-memory DuckDB. Optimizations for handling larger datasets and database scalability are planned.
- **Error Handling in UI:** Error messages are currently primarily logged to the console. Improved error handling and user-friendly error displays within the application UI are needed.
- **Advanced Memory and Context:** Explore techniques like vector embeddings and more structured memory databases for improved conversational context and memory retrieval.
- **Expanded Visualization Types:** Add support for more visualization types beyond the current set.
- **Broader Database Support:** Extend database connectivity to support other popular database systems beyond DuckDB and PostgreSQL.
- **Enhanced Prompt Engineering:** Continuously refine prompts for the LLM to improve accuracy, handle more complex queries, and enhance the overall conversational experience.
- **User Interface Improvements:** Develop a more feature-rich and intuitive user interface for better data exploration and interaction.
- **Data Security and Privacy:** Implement best practices for handling user data and database credentials securely, especially when connecting to external databases.

## Credits and Acknowledgements

- Built using **Streamlit** for the interactive web application framework.
- Leverages **OpenAI's GPT-4o** model for natural language understanding and code generation.
- Utilizes **DuckDB** for fast in-memory database capabilities and **PostgreSQL** for external database connectivity.
- Data manipulation and analysis powered by **pandas**.
- Visualization created with **Plotly**.
- Database interaction using **SQLAlchemy**.

We hope you find Dana a useful tool for exploring and understanding your data!
