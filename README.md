# 🛒 AI E-Commerce Chatbot

An AI-powered e-commerce chatbot that helps users discover products through natural-language queries. It uses semantic search with Sentence Transformers and Redis Vector Search to retrieve relevant products, and Groq's LLM to generate conversational responses.

## ✨ Features

- **Natural-language product search:** Search for products using everyday language.
- **Semantic search:** Finds products based on meaning rather than exact keyword matching.
- **Vector database:** Stores and searches product embeddings using Redis.
- **AI-generated responses:** Uses Groq's LLM to provide conversational answers.
- **Conversation memory:** Maintains chat history for follow-up interactions.
- **Interactive interface:** Provides a chatbot interface using Gradio.

## 🧰 Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core development |
| Pandas & NumPy | Dataset processing |
| Sentence Transformers | Text embeddings |
| Redis Cloud | Vector storage and similarity search |
| LangChain | LLM integration and conversation memory |
| Groq API | AI-powered responses |
| Gradio | Chatbot user interface |

## 🏗️ How It Works

1. **Load the dataset:** Read product information from `product_data.csv`.
2. **Generate embeddings:** Convert product keywords into numerical vectors using `all-distilroberta-v1`.
3. **Store products:** Save product information and embeddings in Redis.
4. **Process user queries:** Use Groq to generate relevant search keywords.
5. **Retrieve products:** Convert the generated keywords into embeddings and perform KNN similarity search in Redis.
6. **Generate responses:** Pass the retrieved product information and user query to the conversational LLM.
7. **Display results:** Show the response through the Gradio chatbot interface.

## 📁 Project Structure

```text
AI-E-Commerce-Chatbot/
│
├── product_data.csv       # Product dataset
├── chatbot.ipynb          # Main project notebook
├── .env                   # API keys and Redis credentials
├── .gitignore
└── README.md
```

*Update `chatbot.ipynb` if your notebook has a different filename.*

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/AI-E-Commerce-Chatbot.git
cd AI-E-Commerce-Chatbot
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it:

**Windows**
```bash
venv\Scripts\activate
```

**Linux / macOS**
```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install gradio redis pandas numpy sentence-transformers python-dotenv
pip install "langchain==0.3.27" "langchain-core==0.3.86" "langchain-groq==0.3.8"
```

### 4. Configure environment variables

Create a `.env` file in the project directory:

```env
REDIS_HOST=your_redis_host
REDIS_PORT=your_redis_port
REDIS_USERNAME=default
REDIS_PASSWORD=your_redis_password
GROQ_API_KEY=your_groq_api_key
```

Replace the placeholder values with your own Redis Cloud and Groq credentials.

### 5. Run the project

Open the notebook in Jupyter Notebook or VS Code, execute the cells in order, and launch the Gradio chatbot interface.

## 🔐 Environment Variables

The project requires:

- `REDIS_HOST` – Redis database hostname.
- `REDIS_PORT` – Redis database port.
- `REDIS_USERNAME` – Redis username.
- `REDIS_PASSWORD` – Redis database password.
- `GROQ_API_KEY` – Groq API key.

**Important:** Never upload your `.env` file or expose API keys and database credentials on GitHub.

Add the following to `.gitignore`:

```gitignore
.env
venv/
__pycache__/
.ipynb_checkpoints/
*.pyc
```

## 🔎 Example Queries

Users can ask questions such as:

- "Show me wireless headphones."
- "I want to buy a laptop for programming."
- "Find products suitable for everyday use."
- "Show me products with useful features."

The chatbot searches the product dataset and generates a response based on the retrieved results.

## 🚀 Future Improvements

- Improve product retrieval relevance.
- Add product category filters.
- Include price-range filtering.
- Add product comparison functionality.
- Improve recommendation quality.
- Deploy the chatbot as a web application.



---

⭐ If you find this project interesting, consider giving the repository a star!
