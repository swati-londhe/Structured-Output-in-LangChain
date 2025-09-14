Structured Data Processing with Pydantic, TypedDict, and LangChain

This project demonstrates multiple approaches for defining and processing structured data in Python using Pydantic, TypedDict, and LangChain. It covers schema validation, JSON schema definitions, and structured output generation from natural language (e.g., processing reviews).

📂 Project Structure

pydantic_demo.py – Defines a Student model with validation (name, age, email, CGPA) using Pydantic. Converts instances to dict and JSON.

typeddict_demo.py – Demonstrates TypedDict with a simple Person schema.

json_schema.json – JSON schema for a student object (name, age, required fields).

with_structured_output_pydantic.py – Uses LangChain with a Pydantic Review model to extract structured info (themes, summary, sentiment, pros, cons, reviewer).

with_structured_output_typeddict.py – Same as above but uses TypedDict.

with_structured_output_json.py – Defines the review schema in JSON and processes output with LangChain.

with_structured_output_llama.py – Uses a HuggingFace model (TinyLlama) with LangChain + Pydantic for structured review extraction.

students_dataset.csv – Placeholder CSV for storing student data (currently empty).

⚙️ Prerequisites

Python 3.8+

Install dependencies:

pip install pydantic langchain langchain-openai langchain-huggingface python-dotenv


API Keys (set in .env file):

OpenAI (for Pydantic/TypedDict/JSON examples):

OPENAI_API_KEY=your_openai_api_key


HuggingFace (for TinyLlama example):

HUGGINGFACEHUB_API_TOKEN=your_huggingface_api_token

🚀 Usage
1. Pydantic Demo
python pydantic_demo.py


Output: Prints the student’s age (e.g., 32) from the dict representation.

2. TypedDict Demo
python typeddict_demo.py


Output:

{'name': 'nitish', 'age': '35'}

3. Structured Output with LangChain

Run any of the scripts:

python with_structured_output_pydantic.py
python with_structured_output_typeddict.py
python with_structured_output_json.py
python with_structured_output_llama.py


Each script processes a Samsung Galaxy S24 Ultra review and extracts structured data.

Example output (Pydantic):

{
  "key_themes": ["performance", "camera", "battery", "S-Pen", "usability", "software", "price"],
  "summary": "The Samsung Galaxy S24 Ultra is a powerful device with a fast processor, excellent camera, and long battery life, but its size, bloatware, and high price are drawbacks.",
  "sentiment": "pos",
  "pros": ["Insanely powerful processor", "Stunning 200MP camera", "Long battery life", "S-Pen support"],
  "cons": ["Heavy and large size", "Bloatware in One UI", "High price"],
  "name": "Nitish Singh"
}

📑 JSON Schema

The json_schema.json file defines a student object schema.
It can be extended to include more fields like email and CGPA for closer alignment with the Pydantic model.

📊 Students Dataset

students_dataset.csv is currently empty.

Intended for storing student records (name, age, email, CGPA) for further validation and processing.

🔮 Future Improvements

Populate students_dataset.csv with sample data.

Add error handling for API key issues and invalid inputs.

Extend json_schema.json with more fields (email, CGPA).

Enable batch processing of multiple reviews.

Compare outputs between OpenAI and HuggingFace models.
