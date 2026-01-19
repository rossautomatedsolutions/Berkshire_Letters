# NLP-Ready Corpus of Berkshire Hathaway Shareholder Letters

This repository provides a small, deterministic ingestion pipeline for assembling a complete corpus of Chairman’s Letters to Shareholders from 1977–present.

The goal is to produce a **stable, NLP-ready document set** that can be reused across experiments without repeated ingestion work.

---

## Motivation

As part of a larger NLP project focused on shareholder communications, I needed a clean and consistent historical dataset.

While Berkshire’s letters are publicly available, their publication format has changed over time:

- Early letters are published as HTML pages  
- Later letters are published directly as PDFs  
- URL patterns and filenames are not consistent across years  

For NLP workflows, this inconsistency leads to unnecessary rework unless ingestion is handled explicitly.

---

## Approach

This repository treats ingestion as a data-engineering problem rather than a scraping problem:

- Each year’s source (HTML or PDF) is explicitly defined in a manifest
- HTML letters are rendered and saved as PDFs
- Existing PDFs are downloaded directly as canonical originals
- All output files follow a single, stable naming convention

The result is a deterministic and reproducible document corpus.

---
