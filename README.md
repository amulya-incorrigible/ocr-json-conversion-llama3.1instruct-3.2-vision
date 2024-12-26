# OCR to JSON Conversion with Llama Models

## Introduction

This project demonstrates the integration of **Optical Character Recognition (OCR)** and **Large Language Models (LLMs)** to extract, process, and structure text from scanned images, such as pharmacy 
invoices. By leveraging the complementary strengths of OCR and LLMs, we aim to solve real-world challenges in data digitization, information retrieval, and automation.

### How It Works

1. **OCR for Text Extraction**:
   OCR tools like [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) specialize in reading and extracting text from scanned images or PDFs. They are efficient in identifying text regions and characters, 
converting them into raw textual data. However, OCR outputs are often unstructured, requiring further processing to extract meaningful insights.

2. **LLMs for Text Understanding and Structuring**:
   Once the raw text is extracted, it is passed to a **Large Language Model (LLM)** such as **Llama 3.1 8B Instruct** or **Llama 3.2 Vision**. These models excel at understanding complex instructions, 
performing semantic analysis, and generating structured outputs like JSON. The LLM interprets the extracted text, identifies key entities (e.g., invoice details, line items), and organizes them into a 
machine-readable format.

3. **Practical Applications**:
   - **Automated Data Entry**: Converting invoices or receipts into structured data reduces manual work, minimizes errors, and saves time.
   - **Streamlining Operations**: Businesses can process large volumes of scanned documents efficiently, such as billing systems, insurance claims, or medical prescriptions.
   - **Enhanced Information Retrieval**: Extracted and structured data can be queried and analyzed, enabling insights and automation.

### Why Combine OCR and LLMs?

While OCR handles the mechanical aspect of recognizing text from images, it lacks the contextual understanding required for downstream tasks. LLMs fill this gap by transforming raw text into actionable 
insights. Together, OCR and LLMs form a powerful pipeline capable of digitizing and structuring unstructured data from scanned documents.

In this project, we demonstrate the practical utility of this pipeline by:
- Extracting text from pharmacy invoices using **PaddleOCR**.
- Leveraging **Llama models** to structure the extracted text into a JSON schema representing invoice details, line items, and totals.

This approach showcases how cutting-edge AI technologies can address real-world problems, making document processing faster, more accurate, and scalable.


---

## Features

- **PDF to Images**: Convert multi-page PDFs into separate JPEG images.
- **OCR Extraction**: Use 
[PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) to read text from 
each page image.
- **LLM-based Parsing**: Feed OCR results into either Llama 3.1 8B 
Instruct or Llama 3.2 Vision to produce a JSON object representing the 
invoice data.
- **JSON Output**: Optionally adapt the JSON schema (e.g., 
`invoiceDetails`, `lineItems`, `totals`, etc.) to your specific use case.

---

## Requirements

Install the following libraries (or similar commands in your environment):

1. **bitsandbytes**
2. **paddleocr**
3. **paddlepaddle-gpu**
4. **pdf2image**
5. **poppler-utils** (system dependency for pdf2image)
6. **opencv-python**
7. **transformers**
8. **huggingface_hub**
9. **accelerate*

## Notes on Models

- **Llama 3.1 8B Instruct**: Text-based large language model.
- **Llama 3.2 Vision**: Includes capabilities for vision inputs, though here we primarily feed it text from OCR.
- Both models can be large and resource-intensive. For smooth operation, an **L4** or **A100 GPU** in Colab is recommended.
- Make sure you request and have access to the **gated Hugging Face repos** for these models.


