Structured Data Processing with Pydantic, TypedDict, and LangChain

This project demonstrates various methods for defining and processing structured data in Python, focusing on Pydantic, TypedDict, and LangChain for structured output generation. It includes examples of schema validation, JSON schema definitions, and processing a review text to extract structured information using different approaches.

Project Structure





pydantic_demo.py: Demonstrates the use of Pydantic for defining a Student model with schema validation, including fields like name, age, email, and CGPA. It creates a student instance and converts it to a dictionary and JSON.



typeddict_demo.py: Shows the use of Python's TypedDict to define a Person schema with name and age fields, and creates an instance of it.



json_schema.json: Defines a JSON schema for a student object with properties like name and age, specifying required fields.



with_structured_output_pydantic.py: Uses LangChain with a Pydantic model (Review) to process a Samsung Galaxy S24 Ultra review and extract structured output (key themes, summary, sentiment, pros, cons, and reviewer name).



with_structured_output_typeddict.py: Similar to the Pydantic version but uses TypedDict for the Review schema to process the same review text.



with_structured_output_json.py: Uses a JSON schema to define the Review structure and processes the review text using LangChain's structured output feature.



with_structured_output_llama.py: Uses a HuggingFace model (TinyLlama) with LangChain and a Pydantic Review model to process the review text.



students_dataset.csv: An empty CSV file (intended for storing student data, but currently empty).

Prerequisites





Python 3.8+



Install required packages:

pip install pydantic langchain langchain-openai langchain-huggingface python-dotenv



For with_structured_output_llama.py, you need a HuggingFace API key. Set it in a .env file:

HUGGINGFACEHUB_API_TOKEN=your_huggingface_api_token



For with_structured_output_pydantic.py, with_structured_output_json.py, and with_structured_output_typeddict.py, you need an OpenAI API key. Set it in a .env file:

OPENAI_API_KEY=your_openai_api_key

Usage





Pydantic Demo:





Run pydantic_demo.py to see how a Student model is defined and validated:

python pydantic_demo.py



Output: Prints the student's age (32) from the dictionary representation.



TypedDict Demo:





Run typeddict_demo.py to see a simple TypedDict example:

python typeddict_demo.py



Output: Prints the Person dictionary ({'name': 'nitish', 'age': '35'}).



Structured Output with LangChain:





Run any of the structured output scripts (with_structured_output_pydantic.py, with_structured_output_typeddict.py, with_structured_output_json.py, or with_structured_output_llama.py):

python with_structured_output_pydantic.py



Each script processes a Samsung Galaxy S24 Ultra review and outputs structured data (key themes, summary, sentiment, pros, cons, and reviewer name).



Example output (varies by script):

{
    'key_themes': ['performance', 'camera', 'battery', 'S-Pen', 'usability', 'software', 'price'],
    'summary': 'The Samsung Galaxy S24 Ultra is a powerful device with a fast processor, excellent camera, and long battery life, but its size, bloatware, and high price are drawbacks.',
    'sentiment': 'pos',
    'pros': ['Insanely powerful processor', 'Stunning 200MP camera', 'Long battery life', 'S-Pen support'],
    'cons': ['Heavy and large size', 'Bloatware in One UI', 'High price'],
    'name': 'Nitish Singh'
}



JSON Schema:





The json_schema.json file defines a schema for student data. It can be used as a reference for validating student-related data in other scripts.



Students Dataset:





The students_dataset.csv file is currently empty. It can be populated with student data (e.g., name, age, email, CGPA) to be used in conjunction with the Pydantic model or other scripts.

Notes





The with_structured_output_llama.py script uses a HuggingFace model (TinyLlama), which may have different performance compared to the OpenAI model used in other scripts.



Ensure you have the .env file configured with the appropriate API keys for OpenAI or HuggingFace, depending on the scripts you run.



The students_dataset.csv file is empty and can be extended to include actual data for further processing or analysis.

Future Improvements





Populate students_dataset.csv with sample data and create a script to process it using Pydantic or LangChain.



Add error handling for API key issues or invalid input data.



Extend the JSON schema in json_schema.json to include more fields like email and CGPA, matching the Pydantic Student model.



Optimize the review processing scripts to handle multiple reviews or larger datasets.
