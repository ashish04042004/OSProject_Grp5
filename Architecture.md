Note: Below is the proposed architecture for the threaded chatbot project.Since the project is in very early stages of development, there may be drastic changes in the provided architecture.
The provided code implements a simple chatbot with a web interface using Python, Flask for the web server, and threading for handling multiple requests simultaneously. Let's break down the architecture:

1. Flask Web Server:
    - The code utilizes the Flask framework to create a web server. Flask is a micro web framework for Python.
    - The `Flask` instance is created with the name `app`.
    - Two routes are defined:
        - `'/'` route renders the `index.html` template.
        - `'/ask'` route handles POST requests from the form in the `index.html` template.

2. Knowledge Base:
    - The `knowledge_base` dictionary contains simple question-answer pairs related to IIT ISM. It's used by the chatbot to provide responses.

3. Chatbot Logic:
    - The `chatbot` function takes a user query, converts it to lowercase, checks if it exists in the knowledge base, and returns the corresponding response.
    - If the query is not in the knowledge base, it returns an error message.

4. User Interface (HTML Templates):
    - The `templates` folder contains an HTML file named `index.html`.
    - This HTML file defines a simple form where users can input their queries.
    - When the form is submitted, the input query is sent to the server for processing.

5. Threading:
    - The code uses Python's `threading` module to run the Flask web server in a separate thread (`flask_thread`).
    - The main thread enters into an infinite loop, ensuring that the main program doesn't exit.
    - This allows the Flask app to run concurrently with other parts of the program.

6. Running the Flask App:
    - The `run_flask` function is defined to start the Flask app in the `flask_thread`.
    - The main program starts the Flask app in a separate thread and enters into a loop to keep the main thread alive.

7. Main Execution:
    - The `if __name__ == '__main__':` block ensures that the code is executed when the script is run directly.
    - It starts the Flask app in a separate thread and keeps the main thread alive.

8. User Interaction:
    - Users interact with the chatbot through a web browser by entering queries in the provided form.
    - The chatbot processes the queries and displays the results on the web page.

Overall, this architecture provides a basic structure for a multi-threaded chatbot with a web interface. .
