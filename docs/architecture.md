# Workflow Architecture

## 1. Overview

This document describes the architecture of the AI-powered invoice extraction and automation workflow built using n8n.

The workflow automates the discovery, processing, extraction, and recording of invoice information from files stored in Google Drive.

## 2. Workflow Components

### A. Workflow Trigger
- The workflow starts through a manual execution trigger in n8n.
- This allows the process to be initiated when invoice files need to be processed.

### B. File Discovery
- Google Drive is used to search for files in the configured folder.
- The workflow loops through the discovered files to process them individually.
- Each file is downloaded for further processing.

### C. File Type Routing
- A Switch node determines the processing path based on the file type.
- PNG files are routed to the image extraction path.
- PDF files are routed to the document extraction path.

### D. Document and Image Extraction
- PDF files are processed through the Extract from File node.
- PNG files are sent through an HTTP Request to the configured OCR service.
- The extracted content is passed to the information extraction stage.

### E. AI-Powered Information Extraction
- The Information Extractor node processes the extracted invoice content.
- Google Gemini is connected as the language model.
- The AI-assisted extraction converts invoice content into structured information.

### F. Data Addition
- Extracted information is sent to Google Sheets.
- The workflow uses an append/update operation to add the extracted information.
- A Split Out node separates line-item information into individual records.
- The resulting records are appended to the spreadsheet.

## 3. End-to-End Workflow

1. Manually trigger the workflow.
2. Search Google Drive for invoice files.
3. Loop through the files.
4. Download each file.
5. Identify whether the file is a PDF or PNG.
6. Process the file through the appropriate extraction path.
7. Use Google Gemini to extract structured invoice information.
8. Add the extracted information to Google Sheets.
9. Split line-item information into individual records.
10. Append the resulting records to the spreadsheet.

## 4. Technology Stack

- n8n Cloud – Workflow orchestration
- Google Drive – Invoice file storage and retrieval
- Google Gemini – AI-powered information extraction
- OCR service – Image text extraction
- Google Sheets – Structured data storage

## 5. Architecture Scope

This document describes the workflow implementation at a component level. It does not include API credentials, private service configurations, confidential invoice data, or authentication details.
