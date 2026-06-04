# File - Retail Sales File

> Copy these prompts into your AI assistant to generate or guide a TIBCO BW6 implementation.

## Overview

A file-polling process that picks up daily retail sales CSV files, parses and maps the records, writes a summary file, and logs the result. Paste the prompts into your AI assistant **one at a time, in order**, and review the generated output in TIBCO Business Studio for BusinessWorks before moving on.

| Prompt | What it does |
|---|---|
| Prompt 1 | Create the BW application |
| Prompt 2 | Create the process and activities |
| Prompt 3 | Configure the activities and error handling |

## Prompt 1 — Create the application

```text
Create a new BW application project named "Retail_Daily_Sales_File".
```

## Prompt 2 — Create the process and activities

```text
Create process:
Name: SalesFileProcessor
Add activities:
File Poller
Parse Data
Mapper
Write File
Log
```

## Prompt 3 — Configure the activities and error handling

> **Before running:** replace the placeholders with paths on your own machine.
> `<INPUT_DIRECTORY>` — the folder to poll for CSV files, e.g. `C:/Retail/Input` (Windows) or `/Users/you/retail/input` (macOS/Linux).
> `<PATH_TO_sales_summary.txt>` — the output file, e.g. `C:/Retail/Output/sales_summary.txt` or `/Users/you/retail/output/sales_summary.txt`.

```text
Configure File Poller:
Directory = <INPUT_DIRECTORY>
Poll for CSV files
Configure Parse Data:
Parse retail sales records
Mapper activity:
Map:
storeName
totalSales
salesDate
Configure Write File:
Output file:
 <PATH_TO_sales_summary.txt>
Configure Log:
Message = "Retail sales file processed"
Add error handling for invalid file formats.
```

## Alternatively — paste all prompts in one go

Prefer to run it as a single prompt? Copy the complete block below into your AI assistant instead of pasting each prompt individually. Remember to replace the `<...>` placeholder(s) with paths on your own machine first.

```text
File-Retail_Sales_File
Create a new BW application project named "Retail_Daily_Sales_File".
Create process:
Name: SalesFileProcessor
Add activities:
File Poller
Parse Data
Mapper
Write File
Log
Configure File Poller:
Directory = <INPUT_DIRECTORY>
Poll for CSV files
Configure Parse Data:
Parse retail sales records
Mapper activity:
Map:
storeName
totalSales
salesDate
Configure Write File:
Output file:
 <PATH_TO_sales_summary.txt>
Configure Log:
Message = "Retail sales file processed"
Add error handling for invalid file formats.
```
