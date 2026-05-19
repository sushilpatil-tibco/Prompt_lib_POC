# JDBC-Retail_inventory_DB

> Copy this prompt into your AI assistant to generate or guide a TIBCO BW6 implementation.

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
FileName ➔ c:/tmp/RetailInventory/inventory_update.log
Configure Node
textContent ➔ concat("inventory records updated: ", string($JDBCUpdate/noOfUpdates))
Activity 5: Log
Configure Node
message ➔ concat("Retail Inventory Process Complete: Updated stock for ", $JDBCQuery/Record[1]/
```
