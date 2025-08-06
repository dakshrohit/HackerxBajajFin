# Intelligent Document Query Retrieval System (RAG)

An advanced RAG (Retrieval-Augmented Generation) application built with TypeScript and Next.js that provides intelligent document analysis and query processing, specifically optimized for insurance policy documents.

![page](https://res.cloudinary.com/dpoiw6a2m/image/upload/v1754486899/Screenshot_From_2025-08-06_18-57-20_d2lxff.png)
![page](https://res.cloudinary.com/dpoiw6a2m/image/upload/v1754486900/Screenshot_From_2025-08-06_18-56-30_phmp7c.png)


## Features

- **Intelligent Query Processing**: Advanced question enhancement with domain-specific patterns
- **Multi-Format Support**: PDF, DOCX, and EML file processing
- **Vector-Based Retrieval**: Custom score-based document retrieval with optimized thresholds
- **Response Caching**: Smart caching system for improved performance
- **Batch Processing**: Parallel question processing with configurable batch sizes
- **Timeout Protection**: Multiple timeout layers for reliable processing
- **Instance Caching**: Cached LLM and embedding instances for optimal performance
- **Technical Accuracy**: Extracts exact numbers, percentages, and specific conditions

## Technologies Used

### **Core Framework**
- **Next.js 14** - React framework for API routes and server-side processing
- **TypeScript** - Type-safe development

### **AI/ML Stack**
- **LangChain.js** - Document processing and retrieval chains
- **Google Generative AI (Gemini 2.0 Flash)** - Large Language Model for text generation
- **Google AI Embeddings (text-embedding-004)** - Vector embeddings for document similarity

### **Vector Database**
- **Supabase Vector Store** - Vector database for document storage and similarity search
- **PostgreSQL with pgvector** - Underlying vector storage engine

### **Document Processing**
- **PDFLoader** - PDF document parsing and text extraction
- **DocxLoader** - Microsoft Word document processing
- **RecursiveCharacterTextSplitter** - Intelligent text chunking with overlap

### **Performance & Optimization**
- **Custom Score Retriever** - Optimized document retrieval with score thresholds
- **Response Caching** - In-memory caching for frequently asked questions
- **Batch Processing** - Parallel question processing for improved throughput
- **Instance Caching** - Cached AI model instances

### **Infrastructure**
- **Supabase** - Database and vector storage
- **Vercel/Node.js** - Deployment platform
- **Buffer API** - File processing and binary data handling

## Installation
- git clone https://github.com/dakshrohit/HackerxBajajFin
- npm install
- npm run dev

### Environmental Variables
- GOOGLE_API_KEY=your_google_ai_api_key
- SUPABASE_URL=your_supabase_url
- SUPABASE_ANON_KEY=your_supabase_anon_key
- AUTHORIZATION_KEY=your_api_authorization_key

## Usage

### API Endpoint

POST /api/process

Headers:
Authorization: Bearer <your-api-key>
Content-Type: application/json

Body:
{
"documents": "https://example.com/document.pdf",
"questions": [
"What is the grace period for premium payment?",
"What are the waiting periods for pre-existing diseases?",
"What is the coverage for maternity expenses?"
]
}

### Response Format

{
"answers": [
"The grace period is 30 days from the premium due date. Coverage is not available if premium isn't received.",
"Pre-existing diseases are excluded for 36 months from the first policy inception date...",
"Yes, maternity expenses are covered with a 24-month waiting period for females aged 18-45 years..."
]
}


## Key Features

### **Intelligent Query Enhancement**
- Domain-specific pattern matching
- Automatic question enhancement for better retrieval
- Number-focused query optimization

### **Advanced Document Retrieval**
- Custom score-based retrieval with 0.3 threshold
- Processes 20 documents per query for comprehensive coverage
- 1500-character chunks with 300-character overlap

### **Performance Optimizations**
- Batch processing with configurable size (default: 2)
- Response caching for identical questions
- Parallel processing with Promise.allSettled
- Multiple timeout protection layers (30s primary, 20s retry)

### **Response Quality**
- Yes/No format detection for applicable questions
- Concise-medium length responses (50 words max)
- Maximum numerical accuracy with specific timeframes
- Plan variation comparisons (Plan A vs Plan B vs Plan C)

## Performance Metrics

- **Processing Speed**: 35-50% faster with caching
- **Accuracy**: Superior technical detail extraction
- **Concurrency**: Up to 4 parallel LLM calls
- **Cache Hit Rate**: Near-instant responses for repeated questions

## Supported File Types

- **PDF** (.pdf) - Complete text extraction and processing
- **DOCX** (.docx) - Microsoft Word document support
- **EML** (.eml) - Email file processing

## System-Architecture
Document URL → File Processing → Text Chunking → Vector Storage
                                                      ↓
Question → Enhancement → Retrieval → LLM Processing → Response
                                     ↑
                              Response Cache ←


### LICENSE 

MIT License

Copyright (c) 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


              
