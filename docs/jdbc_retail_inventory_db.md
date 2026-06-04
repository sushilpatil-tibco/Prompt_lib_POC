# JDBC - Retail Inventory DB

> Copy these prompts into your AI assistant to generate or guide a TIBCO BW6 implementation.

## Overview

A scheduled retail inventory process that queries product details from a database, decrements stock levels, and logs the results to a file. Paste the prompts into your AI assistant **one at a time, in order**, and review the generated output in TIBCO Business Studio for BusinessWorks before moving on.

| Prompt | What it does |
|---|---|
| Prompt 1 | Project overview and target runtime |
| Prompt 2 | Module and process properties |
| Prompt 3 | Shared resources (JDBC connection) |
| Prompt 4 | Process logic and activity configuration |

## Prompt 1 — Project overview

```text
Retail Inventory JDBC Processing Example
Project Name
retail.bw.sample.palette.jdbc.InventoryUpdate
Target Runtime
TIBCO ActiveMatrix BusinessWorks™ 6.x
Description
A scheduled retail inventory management process that retrieves product details from a retail database, updates inventory stock levels, and logs processing results to a file.
```

## Prompt 2 — Module and process properties

```text
Project Hierarchy
Module Properties Configuration
Create and configure the following properties:
Process Properties Configuration
```

## Prompt 3 — Shared resources

```text
Shared Resources
JDBC Connection
Name
RetailDBConnection
All values should come from the module properties created above.
```

## Prompt 4 — Process logic and activities

> **Before running:** replace `<PATH_TO_inventory_update.log>` with the output log path on your own machine.
> Example: `c:/tmp/RetailInventory/inventory_update.log` (Windows) or `/tmp/retail/inventory_update.log` (macOS/Linux).

```text
Process Logic
Process Name
Process.bwp
Create the following activities in sequence and link them:
Timer
JDBC Query
JDBC Update
Write File
Log
Activity Configurations
Activity 1: Timer (Starter)
Activity 2: JDBC Query
SQL Statement
SELECT PRODUCT_ID, PRODUCT_NAME, STOCK_QUANTITY
FROM PRODUCT_TABLE
WHERE PRODUCT_ID = ?
Configure Node
product_id ➔ $product_id
Ensure $product_id is defined as a process variable.
Activity 3: JDBC Update
SQL Statement
UPDATE PRODUCT_TABLE
SET STOCK_QUANTITY = STOCK_QUANTITY - 1
WHERE PRODUCT_ID = ?
Configure Node
jdbcUpdateActivityInput ➔ $JDBCQuery/Record[1]
Activity 4: Write File
Configure Attribute
FileName ➔ <PATH_TO_inventory_update.log>
Configure Node
textContent ➔ concat("inventory records updated: ", string($JDBCUpdate/noOfUpdates))
Activity 5: Log
Configure Node
message ➔ concat("Retail Inventory Process Complete: Updated stock for ", $JDBCQuery/Record[1]/
```

## Alternatively — paste all prompts in one go

Prefer to run it as a single prompt? Copy the complete block below into your AI assistant instead of pasting each prompt individually. Remember to replace the `<...>` placeholder(s) with paths on your own machine first.

```text
JDBC-Retail_inventory_DB
Retail Inventory JDBC Processing Example
Project Name
retail.bw.sample.palette.jdbc.InventoryUpdate
Target Runtime
TIBCO ActiveMatrix BusinessWorks™ 6.x
Description
A scheduled retail inventory management process that retrieves product details from a retail database, updates inventory stock levels, and logs processing results to a file.
1. Project Hierarchy
2. Module Properties Configuration
Create and configure the following properties:
3. Process Properties Configuration
4. Shared Resources
JDBC Connection
Name
RetailDBConnection
All values should come from the module properties created above.
5. Process Logic
Process Name
Process.bwp
Create the following activities in sequence and link them:
Timer
JDBC Query
JDBC Update
Write File
Log
Activity Configurations
Activity 1: Timer (Starter)
Activity 2: JDBC Query
SQL Statement
SELECT PRODUCT_ID, PRODUCT_NAME, STOCK_QUANTITY
FROM PRODUCT_TABLE
WHERE PRODUCT_ID = ?
Configure Node
product_id ➔ $product_id
Ensure $product_id is defined as a process variable.
Activity 3: JDBC Update
SQL Statement
UPDATE PRODUCT_TABLE
SET STOCK_QUANTITY = STOCK_QUANTITY - 1
WHERE PRODUCT_ID = ?
Configure Node
jdbcUpdateActivityInput ➔ $JDBCQuery/Record[1]
Activity 4: Write File
Configure Attribute
FileName ➔ <PATH_TO_inventory_update.log>
Configure Node
textContent ➔ concat("inventory records updated: ", string($JDBCUpdate/noOfUpdates))
Activity 5: Log
Configure Node
message ➔ concat("Retail Inventory Process Complete: Updated stock for ", $JDBCQuery/Record[1]/
```
