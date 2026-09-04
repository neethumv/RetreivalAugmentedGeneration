# RAG Assignment Using Databricks Vector Search

## Overview

This project demonstrates the implementation of a Retrieval-Augmented Generation (RAG) pipeline using a collection of HR policy and process documents.

The solution includes document chunking, embedding generation, vector indexing, semantic retrieval, metadata filtering, groundedness validation, and hybrid retrieval.

## Documents Used

- GDPR Employee Data Practices
- HR Quarterly Summary
- Performance Calibration Guide
- Security Awareness Brief
- Travel Policy Quick Reference
- DEI Program Outline
- Exit Process Checklist
- Flexible Work Toolkit

## Scenarios Completed

### 1. Baseline RAG Pipeline
- Extracted text from PDF documents
- Created document chunks
- Generated embeddings
- Built a Vector Search index
- Retrieved relevant content and answered questions with source citations

### 2. Chunking Tradeoffs
Compared two chunking strategies:

- 200 tokens with 50-token overlap
- 800 tokens with 100-token overlap

**Finding:** Larger chunks provided better context for policy and process-based documents, while smaller chunks improved precision but sometimes returned incomplete information.

### 3. Metadata-Filtered Retrieval
Added document metadata such as topic/category and used filters during retrieval.

Examples:
- GDPR queries → GDPR documents only
- Travel queries → Travel Policy documents only

**Result:** Improved retrieval relevance and reduced unrelated context.

### 4. Groundedness Failure Hunt
Tested questions not covered by the document collection.

Example:
> What is the company stock option vesting schedule?

The system was updated to respond with:
> "Information not found in the provided documents."

**Result:** Eliminated hallucinated responses.

### 5. Hybrid Retrieval
Combined:
- Semantic vector search
- Keyword-based matching

Example:
> What is DSAR?
**Result:** Hybrid retrieval located exact references more accurately than pure semantic search.

## Key Learnings

- RAG improves answer quality by grounding responses in enterprise documents.
- Chunk size significantly influences retrieval performance.
- Metadata filtering improves retrieval precision.
- Groundedness checks help prevent hallucinations.
- Hybrid retrieval is effective for exact references and identifiers.

## Conclusion

The project successfully implemented and evaluated a Databricks-based RAG solution across multiple retrieval scenarios, demonstrating best practices for enterprise document search and question answering.
