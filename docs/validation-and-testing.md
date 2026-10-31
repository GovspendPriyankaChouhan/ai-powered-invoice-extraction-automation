# Validation and Testing

## 1. Overview

This document describes the validation and testing approach for the AI-powered invoice extraction and automation workflow built using n8n.

The workflow was implemented and tested to verify its file-processing, extraction, and Google Sheets integration stages.

## 2. Testing Scope

The testing covered the following workflow components:

- Google Drive file discovery
- File download and loop processing
- PDF and PNG file routing
- Document and image text extraction
- AI-powered information extraction using Google Gemini
- Structured invoice data processing
- Line-item separation using the Split Out node
- Google Sheets append/update operations

## 3. Test Scenarios

| Test ID | Component | Validation Objective | Status |
|---|---|---|---|
| T01 | Manual Trigger | Verify that the workflow starts successfully | Tested |
| T02 | Google Drive | Verify invoice file discovery | Tested |
| T03 | File Download | Verify that discovered files are downloaded | Tested |
| T04 | File Routing | Verify PDF and PNG processing paths | Tested |
| T05 | Document Extraction | Verify extraction of PDF content | Tested |
| T06 | Image Extraction | Verify OCR processing of PNG files | Tested |
| T07 | Information Extractor | Verify AI-assisted information extraction | Tested |
| T08 | Google Sheets | Verify that extracted information is added to the spreadsheet | Tested |
| T09 | Line-item Processing | Verify that line items are separated and appended | Tested |

## 4. Validation Approach

The workflow was evaluated by checking:

- Successful execution of the connected n8n nodes.
- Correct routing of supported file types.
- Availability of extracted information for downstream processing.
- Successful transfer of structured information to Google Sheets.
- Processing of individual line items through the Split Out stage.

## 5. Expected Outcome

The workflow is designed to automate the movement of invoice information from source documents into structured spreadsheet records, reducing repetitive manual processing.

## 6. Project Status

The workflow has been implemented and tested in n8n Cloud.

This document records the testing scope and validation approach for the portfolio demonstration.
