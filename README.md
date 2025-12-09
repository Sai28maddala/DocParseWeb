#  DocParseWeb

DocParseWeb is an **end-to-end document parsing and extraction system** built using **FastAPI + PyMuPDF + MongoDB**.  
It converts PDFs into **clean structured JSON**, extracts metadata, supports multi-page text processing, and provides a **web interface + REST API** for uploading and managing documents.

> Upload PDF → Parse → Clean → Extract → Store → Retrieve as JSON  
> Ideal for research workflows, academic pipelines, and automated document processors.

---

##  Key Features

- **PDF Parsing & Extraction**
  - Extracts clean text from multi-page PDFs.
  - Supports metadata extraction (author, title, creation date, etc.).
  - Handles scanned PDFs using optional OCR (Tesseract-ready structure).

- **Structured JSON Output**
  - Page-level text blocks
  - Metadata section
  - Unified JSON schema for downstream ML/NLP tasks

- **FastAPI Backend**
  - REST API for upload, parse, fetch, delete
  - Async processing for large documents
  - Auto-generated docs via Swagger & ReDoc

- **MongoDB Integration**
  - Each parsed document stored as a structured record
  - Easy retrieval & search
  - Supports versioning & history

- **Web UI**
  - Simple, clean interface for uploading PDFs  
  - Displays parsed output & metadata  
  - Designed for research / annotation workflows  

- **Modular Architecture**
  - Clear separation of:
    - PDF parsing logic
    - Database operations
    - API routes
    - Frontend templates

---

##  Architecture Overview

```text
Client (Web UI / API Client)
       |
       v
[ FastAPI Backend ]
  - /upload
  - /parse
  - /docs
       |
       v
[ Parser Engine ]
  - PyMuPDF text extraction
  - OCR (optional)
  - JSON structuring
       |
       v
[ MongoDB ]
  - Stores parsed results
  - Stores metadata
