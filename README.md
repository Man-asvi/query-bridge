# Query Bridge

Query Bridge is a powerful web application that translates natural language questions into executable SQL queries. It allows users to interact with their tabular data using plain English, see the results instantly, and get a clear explanation of the underlying SQL code. This tool is built with React, Google's Gemini AI, and an in-browser SQL database, making it a seamless and educational experience for both technical and non-technical users.

## ✨ Features

*   **Natural Language to SQL:** Ask questions like "How many female students are placed?" and get a valid SQL query in return.
*   **In-Browser SQL Execution:** Runs the generated SQL query against the provided data directly in your browser using SQL.js, ensuring data privacy and speed.
*   **Custom Data Upload:** Start with the provided sample placement dataset or upload your own CSV file to query your own data.
*   **SQL Explanation:** Don't just get the query, understand it. The app uses AI to explain what the generated SQL does in simple terms.
*   **Dynamic Schema Awareness:** The AI is provided with the specific schema of the loaded data, enabling it to generate accurate and context-aware queries.
*   **Error Handling & Validation:** Includes checks to prevent the execution of queries that reference non-existent columns, providing helpful feedback to the user.
*   **Responsive UI:** A clean and modern interface built with Tailwind CSS that works on all screen sizes.

## 🛠️ Technology Stack

*   **Frontend:** [React](https://react.dev/), [TypeScript](https://www.typescriptlang.org/), [Tailwind CSS](https://tailwindcss.com/)
*   **AI / NLP:** [Google Gemini API](https://ai.google.dev/)
*   **In-Browser Database:** [SQL.js](https://sql.js.org/) (SQLite compiled for the web)
*   **CSV Parsing:** [PapaParse](https://www.papaparse.com/)
*   **Build Tool:** [Vite](https://vitejs.dev/)

## ⚙️ How It Works

The application follows a simple yet powerful workflow:

1.  **Data Loading:** On startup, the app loads a sample CSV dataset into an in-browser SQL.js database. Users can also provide their own CSV data, which will replace the sample data.
2.  **Schema Generation:** The application inspects the loaded data to generate a database schema. This schema, including table name, column names, and data types, is crucial for providing context to the AI.
3.  **Query Generation:** When a user submits a natural language question:
    *   The question and the database schema are sent to the Google Gemini API.
    *   The Gemini model is prompted to act as a SQL expert and generate a single, executable SQL statement.
4.  **Query Execution:** The generated SQL query is executed against the in-browser SQL.js database.
5.  **Display Results:** The results from the query are formatted and displayed in a clear, readable table.
6.  **Explanation (Optional):** If the user clicks "Explain SQL," the generated query is sent back to the Gemini API with a prompt asking for a step-by-step explanation of what the code does.

## 🚀 Getting Started (Local Development)

Follow these instructions to set up and run the project on your local machine.

### Prerequisites

*   [Node.js](https://nodejs.org/) (version 18 or higher recommended)
*   `npm` or a compatible package manager
*   A [Google Gemini API Key](https://ai.google.dev/tutorials/setup).

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/query-bridge.git
    cd query-bridge
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Set up environment variables:**
    *   Create a new file in the root of the project named `.env`.
    *   Add your Google Gemini API key to this file:

    ```env
    # .env
    GEMINI_API_KEY="YOUR_API_KEY_HERE"
    ```

4.  **Run the development server:**
    ```bash
    npm run dev
    ```
    The application should now be running locally, typically at `http://localhost:5173`.
