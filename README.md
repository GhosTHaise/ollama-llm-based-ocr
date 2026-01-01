# Ollama LLM-Based OCR

This project demonstrates the use of the Ollama LLM (Large Language Model) for Optical Character Recognition (OCR) and structured data extraction from images of receipts. The workflow involves analyzing an image, extracting text, and converting the extracted data into structured formats such as JSON and Pandas DataFrames.

## Features
- **Image Analysis**: Uses the Ollama LLM to analyze images and extract textual data.
- **Structured Data Extraction**: Converts the extracted text into a structured JSON format.
- **Data Transformation**: Parses the JSON data and converts it into a Pandas DataFrame for further analysis.
- **Customizable Templates**: Allows customization of the fields to extract from the receipt.

## Workflow
1. **Load and Analyze the Image**:
   - The image is analyzed using the Ollama LLM (e.g., `llama3.2-vision`).
   - Extracts all textual data from the image.

2. **Structured JSON Output**:
   - A predefined template is used to extract specific fields from the text, such as:
     - Company
     - Bill To (Name, Address)
     - Ship To (Name, Address)
     - Receipt Number
     - Date
     - Items (Description, Quantity, Unit Price, Total)
     - Subtotal, Sales Tax, Total
     - Payment Instructions
     - Terms & Conditions

3. **Data Parsing**:
   - Extracts the JSON data using regex.
   - Parses the JSON into a Python dictionary.

4. **Data Transformation**:
   - Converts the parsed JSON data into a Pandas DataFrame.
   - Adds general receipt details as columns to the DataFrame.

## Prerequisites
- Python 3.8+
- Required Python libraries:
  - `ollama`
  - `langchain_ollama`
  - `pandas`
  - `re`
  - `json`

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/GhosTHaise/ollama-llm-based-ocr.git
   ```
2. Navigate to the project directory:
   ```bash
   cd ollama-llm-based-ocr
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. Place the image of the receipt in the `pics` directory.
2. Update the `image_path` variable in the notebook or script with the path to your image.
3. Run the notebook `main.ipynb` to execute the workflow.

## Output
- **JSON File**: Structured data extracted from the receipt.
- **Pandas DataFrame**: Tabular representation of the receipt details.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments
- [Ollama LLM](https://ollama.ai/) for providing the language model.
- [LangChain](https://www.langchain.com/) for the prompt and output parsing utilities.
- [source](https://www.youtube.com/watch?v=Huy-Gn4RtGQ) for the idea of using the Ollama LLM for OCR.