# Travel Agent Chatbot

Welcome to the Travel Agent Chatbot project. This chatbot is designed to assist customers of a travel company by answering their queries using a combination of retrieval-augmented generation (RAG), Google's Gemini language model, and ChromaDB for knowledge storage. The chatbot retrieves relevant information from a knowledge base, generates helpful responses, and maintains conversation history to provide context-aware answers.

---

## Features

- **Retrieval-Augmented Generation (RAG):** Utilizes DPR-based embeddings to retrieve travel-related information.
- **Conversational Memory:** Remembers previous interactions to provide context-aware responses.
- **Google Gemini Integration:** Uses Google's Gemini API for generating responses.
- **ChromaDB for Knowledge Storage:** Stores and retrieves travel-related information efficiently.
- **Admin Commands:** Supports the manual addition of new knowledge during runtime.
- **Customizable Knowledge Base:** Load your own travel-related data to expand the chatbot's knowledge.

---

## Installation & Setup

### Prerequisites

Before you begin, ensure you have:
- Python 3.9 or higher
- pip and virtualenv (a virtual environment is recommended)
- A valid Google Gemini API key
- ChromaDB installed

### Cloning the Repository

Clone the repository and navigate into the project directory:

```sh
git clone https://github.com/your-repo/travel-agent-chatbot.git
cd travel-agent-chatbot
```

### Setting Up a Virtual Environment (Recommended)

Create and activate a virtual environment:

```sh
python -m venv venv
# On macOS/Linux:
source venv/bin/activate
# On Windows:
venv\Scripts\activate
```

### Installing Dependencies

Install the required packages using the following command:

```sh
pip install -r requirements.txt
```

### Configuring Environment Variables

Create a `.env` file in the root directory of the project and add your Google Gemini API key:

```env
GEMINI_API_KEY=your_google_gemini_api_key
```

---

## Usage

### Starting the Chatbot

To run the chatbot, execute the following command:

```sh
python chatbot.py
```

### Loading a Knowledge Base

You can load an existing knowledge base from a text file. For example:

```python
kb_file = "path/to/your/travel_company_kb.txt"
num_paragraphs = chatbot.load_knowledge_base(kb_file)
print(f"Loaded {num_paragraphs} paragraphs into the knowledge base")
```

### Interacting with the Chatbot

Simply type your travel-related query at the prompt. For example:

```
Customer: What are the visa requirements for traveling to France?
Agent: Visa requirements vary depending on your nationality. Based on our knowledge base, ...
```

### Admin Commands

You can also add new knowledge to the database while the chatbot is running:

- To add new information, type:
  
  ```
  !add <your text here>
  ```

- Example:
  
  ```
  !add Travel insurance is recommended for international travelers.
  System: Added new knowledge with ID: 1234abcd
  ```

---

## Troubleshooting

### ChromaDB Storage Issues

- If ChromaDB fails to initialize or the knowledge base doesn't load correctly, verify that the `./chroma` directory exists and is accessible.
- If you suspect the database is corrupted, delete the `./chroma` folder and restart the chatbot to rebuild the database.

### API Key Errors

- Ensure that your Google Gemini API key is correctly set in the `.env` file.
- If authentication fails, consider regenerating the API key from the Google Cloud Console.

### Knowledge Base Loading Issues

- Confirm that the knowledge base file exists at the specified path.
- Verify that the file is formatted correctly, with paragraphs separated by double line breaks (`\n\n`).

---

## Future Improvements

- **Multi-language Support:** Enable the chatbot to handle queries in multiple languages.
- **Integration with Booking APIs:** Connect the chatbot with travel booking platforms for real-time information.
- **Voice Interface:** Develop a voice-enabled assistant for hands-free travel planning.

---

## Contributions

Contributions to this project are welcome. Please feel free to fork the repository and submit pull requests with improvements or bug fixes.

---

## License

This project is licensed under the MIT License. You are free to modify and use it for your own travel-related projects.

---

This README should provide a clear and human-friendly guide to understanding, installing, and using the Travel Agent Chatbot. If you have any questions or need further assistance, please feel free to reach out.
