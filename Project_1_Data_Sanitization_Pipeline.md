# Project 1: Automated Data Cleansing and Keyword Sanitization Pipeline

### Project Overview
In search marketing operations, managing large keyword datasets of over 400+ rows across platforms like Google Keyword Planner often results in critical database failures. Raw text sheets usually contain minor anomalies such as extra spaces, trailing slashes, hyphens, and unmatched parentheses (spaces, -, /, ()). When linking this data via Excel formulas, these minor text bugs cause VLOOKUP to fail entirely with #N/A errors. 

This project demonstrates how I resolved this by designing an AI-driven data cleansing prompt. Instead of manually cleaning hundreds of rows line-by-line, which takes hours of manual labor, I engineered a system prompt that sanitized Column F within seconds. This approach achieved a perfect data match without altering any surrounding data rows or formulas in the master sheet.

### Practical Bottlenecks and Constraints
* The Problem: Structural text anomalies corrupted the automated data extraction, breaking downstream spreadsheet linking and causing critical data gaps (#N/A errors).
* The Constraint: The prompt had to strictly modify only Column F. It had to keep all surrounding columns completely untouched, ensuring zero cell-shifting or matrix corruption in the master spreadsheet.

### Prompt Engineering Execution Steps
1. Text Boundary Mapping: I wrapped the raw keyword data inside explicit text boundary blocks so the model could isolate variables cleanly without mixing them with instructions.
2. Localized Boundaries: Implemented strict system instructions defining Column F as the sole target. This prevented the model from altering the matrix alignment or row indices of adjacent columns.
3. Verification Loop: The prompt instructed the model to return an array of identical length alongside a brief operational log verifying the specific cleaning steps taken.
4. Operational Metrics: The clean keyword stream achieved a 100% pass rate when run through Keyword Planner and re-linked via VLOOKUP. This completely eliminated downstream #N/A errors and reduced data-cleaning time by over 95%.
