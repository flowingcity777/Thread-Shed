# Thread Shed - Data Cleaning & Sales Analysis

A Python-based data cleaning and analysis script designed to process, format, and extract insights from a legacy, unformatted string of daily transaction records. This project demonstrates foundational string manipulation, data parsing, and aggregation workflows in Python.

## Project Description

Thread Shed is a boutique textile shop that tracks its daily sales using an automated register system. However, the system outputs data as one massive, poorly formatted string filled with mixed delimiters (`;,;`), trailing whitespaces, and un-separated multi-color transactions (e.g., `white&blue`). 

This script automates the end-to-end data pipeline to:
1. **Clean & Parse:** Standardize delimiters, strip erroneous newlines, and remove whitespace from transaction records.
2. **Unpack Fields:** Isolate customer names, individual sale totals, and thread colors into dedicated lists.
3. **Financial Aggregation:** Convert currency strings into floating-point numbers to calculate the exact total revenue for the day.
4. **Inventory Analysis:** Flatten multi-color data entries (splitting items combined with `&`) and implement an iterative counting mechanism to determine exactly how many units of each distinct thread color were sold.

## Features

- **Robust String Cleaning:** Leverages chaining methods like `.replace()`, `.split()`, and `.strip()` to normalize highly irregular raw text data.
- **Custom Analysis Algorithms:** Features a dedicated iterative scanning function to precisely aggregate individual items from multi-valued fields.
- **Formatted Financial Reports:** Outputs a clean summary of total sales utilizing pythonic float mapping and currency formatting.

## Code Overview & Architecture

The script processes data sequentially through the following pipeline stages:

1. **Delimiter Normalization:** Converts complex nested delimiters (`;,;`) into a clean single character indicator (`;`).
2. **Data Splitting:** Segregates individual customer transactions by splitting on commas.
3. **List Comprehension & Stripping:** Sanitizes raw artifacts (`\n`) and leading/trailing spaces across all structural fields.
4. **Structural Unpacking:** Segregates the multi-dimensional transaction records down into synchronized sub-lists: `customers`, `sales`, and `thread_sold`.
5. **Color Flattening:** Iterates over the separated thread data, parsing complex strings like `"white&blue"` into independent list items (`"white"`, `"blue"`).
6. **Metrics Iteration:** Loops through the core product inventory array to count and report total units sold per color category.

## Usage

To execute the script and generate the sales report, run the file directly using Python:

```bash
python thread_shed.py
