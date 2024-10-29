## RAG-based Chatbot with Contextual Retrieval and Token Management

This project implements a chatbot that uses a Retrieval-Augmented Generation (RAG) approach, leveraging OpenAI embeddings, FAISS for vector storage, and LangChain’s ConversationalRetrievalChain for conversational memory. The chatbot provides responses based solely on a given context and past chat history, and prompts the user to rephrase or ask more specific questions when token limits are exceeded.

## Project Structure
- data: Contains example conversation history used for context in this project.
- vectorstore.py: Script to create embeddings for context and store them in a FAISS vector database.
- app.py: Main application to initialize the chatbot, manage user interactions, and handle token limits.

## Contextual Retrieval:
- Uses FAISS for efficient retrieval of relevant context based on user queries.
- Ensures the chatbot only responds with answers from the available context. If a question is outside the given context, the bot responds, "I don’t have information on that topic."

## Prompting Technique:
- The chatbot uses a prompt template with the following structure:
- Context: Relevant information extracted from FAISS based on user input.
- Chat History: Logs previous interactions to maintain conversational continuity.
- User Query: The latest question posed by the user.
- This ensures that responses are tailored to the provided context.

## Token Management:
- To prevent exceeding token limits, the chatbot calculates the total tokens (including chat history, context, and user question).
- If the total tokens exceed the specified limit (e.g., 225 tokens), the chatbot prompts the user to ask a more specific question.

## Installation
Clone the repository:
git clone <repository-url>

## Install dependencies:
```
pip install -r requirements.txt
```

Run app.py to start the chatbot.
'''
python app.py
'''

- Interact with the chatbot by asking questions. The chatbot will respond based on the available context.
- If the response exceeds the token limit, a prompt will guide the user to ask a more focused question.

## Example Output
- When the user asks a question, the chatbot: Retrieves the most relevant context.
- Responds with an answer based on the context and chat history.
- If token limits are exceeded, displays a message: "The response is too long. Please ask a more specific question."
Files

## Notebook: 
A Colab notebook detailing the code and execution steps for ease of reference and testing.

Notes : The chatbot’s behavior and retrieval strategy can be adapted to handle larger contexts by adjusting the token limits and memory management settings.

