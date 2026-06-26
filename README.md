# get-brochure
This is a project to get a brochure of a company by using the data of their company website
# AI Company Brochure Generator

An AI-powered application that automatically generates a professional company brochure by scraping a company's website and using a Large Language Model (LLM) to summarize the content into a well-structured Markdown document.

The project extracts the most relevant pages from a website (such as **About**, **Company**, and **Careers**) and uses an LLM to generate a concise brochure suitable for prospective customers, investors, and job seekers.

---

## Features

* Scrapes a company's website.
* Automatically identifies important links (About, Careers, Company, etc.).
* Extracts webpage content.
* Uses an LLM (Ollama or Groq API) to summarize the information.
* Streams the generated brochure in real time.
* Outputs the brochure in Markdown format.

---

## Technologies Used

* Python 3.10+
* OpenAI Python SDK (compatible with Ollama and Groq)
* Ollama (Local LLM) **or** Groq API
* Jupyter Notebook
* IPython
* JSON

---

## Project Structure

```
project/
│
├── main.py
├── scraper.py
├── README.md
└── requirements.txt
```

---

## Required Python Modules

Install all dependencies using:

```bash
pip install -r requirements.txt
```

Or install them manually:

```bash
pip install openai
pip install requests
pip install beautifulsoup4
pip install lxml
pip install ipython
```

### Modules Used

| Module          | Purpose                                         |
| --------------- | ----------------------------------------------- |
| openai          | Connects to Ollama or Groq API                  |
| requests        | Downloads webpage HTML                          |
| beautifulsoup4  | Parses HTML pages                               |
| lxml            | HTML parser                                     |
| json            | Parses JSON responses                           |
| os              | Operating system utilities                      |
| IPython.display | Streams Markdown output inside Jupyter Notebook |

---

## Running the Project

### Option 1: Using Ollama

1. Install Ollama.

2. Pull a model.

Example:

```bash
ollama pull llama3.2
```

or

```bash
ollama pull qwen3:8b
```

3. Start the Ollama server.

4. Set

```python
MODEL = "llama3.2"
```

or

```python
MODEL = "qwen3:8b"
```

---

### Option 2: Using Groq API

Create a Groq API key from the Groq Console.

Configure the client:

```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_GROQ_API_KEY",
    base_url="https://api.groq.com/openai/v1"
)
```

Example model:

```python
MODEL = "llama-3.3-70b-versatile"
```

---

## Running the Notebook

This project is designed to run inside **Jupyter Notebook**.

Install Jupyter:

```bash
pip install notebook
```

Start Jupyter:

```bash
jupyter notebook
```

Open the notebook and run all cells.

> **Note:** The streaming output uses `IPython.display`, so real-time Markdown updates work correctly only in Jupyter Notebook (or other notebook environments that support IPython display updates).

---

## How It Works

1. User enters the company name and website URL.
2. The scraper collects all hyperlinks from the landing page.
3. The LLM selects the most relevant pages.
4. The scraper downloads the contents of those pages.
5. The LLM generates a concise brochure in Markdown.
6. The brochure is streamed live to the notebook.

---

## Example

Input

```
Company Name:
OpenAI

Website:
https://openai.com
```

Output

```
# OpenAI

## About

...

## Products

...

## Careers

...

## Company Culture

...
```

---

## Future Improvements

* Export brochure as PDF
* Export brochure as DOCX
* Streamlit web interface
* Gradio interface
* Multi-language brochure generation
* Company logo extraction
* Image support
* Better prompt engineering
* Error handling and retries

---

## Author

**Palam Chaitanya Reddy**

B.Tech in Electronics and Communication Engineering

IIIT Kottayam

---

## License

This project is intended for educational and learning purposes.
