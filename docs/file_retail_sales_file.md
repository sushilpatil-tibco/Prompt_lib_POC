# File-Retail_Sales_File

> Copy this prompt into your AI assistant to generate or guide a TIBCO BW6 implementation.

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
Directory = C:/Retail/Input
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
 C:/Retail/Output/sales_summary.txt
Configure Log:
Message = "Retail sales file processed"
Add error handling for invalid file formats.
```
