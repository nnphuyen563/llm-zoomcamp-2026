# LLMs
An LLM (Large Language Model) is a **neural network** trained on massive amounts of text. Given a prompt, it generates a continuation - a plausible next piece of text.

But LLMs have limitations:
- Knowledge cutoff
- No access to your data
- Hallucinations

# Environment setup
### Creating the project locally
```
curl -LsSf https://astral.sh/uv/install.sh | sh
```
uv is an extremely fast, next-generation package and project manager for Python, written in Rust

### Adding dependencies
```
uv init
uv add requests minsearch openai jupyter python-dotenv
```
This installs:

- `requests` - to fetch the FAQ dataset from the internet
- `minsearch` - a simple in-memory search engine for indexing and searching text
- `openai` - the OpenAI API client for calling the LLM
- `jupyter` - the notebook environment where we'll write and run code
- `python-dotenv` - to load API keys from a .env file

### Setting up API keys
1. Create `.gitignore`, `.env` inside code folder

2. Put API key into `.env`
```
OPENAI_API_KEY=sk-YOUR_KEY_HERE
```

3. Now add `.env` to `.gitignore` to make sure you never accidentally commit your key

### Starting Jupyte
1. Start Jupyter:
```
uv run jupyter notebook
```
2. Create a new notebook

3. Check that the OpenAI client works inside notebook:
```
from dotenv import load_dotenv
load_dotenv()
```
```
from openai import OpenAI
openai_client = OpenAI()    
```

*Note: If uv didn't work, using !pip install directly in `.ipynb`
