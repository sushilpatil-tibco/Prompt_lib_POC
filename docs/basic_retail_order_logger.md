# Basic Retail Order Logger

> Copy these prompts into your AI assistant to generate or guide a TIBCO BW6 implementation.

## Overview

This page breaks the **Basic Retail Order Logger** build into sequential prompts. Paste them into your AI assistant **one at a time, in order**, and review the generated output in TIBCO Business Studio for BusinessWorks before moving on.

| Prompt | What it does |
|---|---|
| Prompt 1 | Create the BW application project |
| Prompt 2 | Create the main process (`OrderProcess`) |
| Prompt 3 | Create the validation subprocess (`ValidateOrder`) |
| Prompt 4 | Add schemas and resources |
| Prompt 5 | Define module properties |
| Prompt 6 | Configure activities in the main process |
| Prompt 7 | Configure activities in the subprocess |

## Prompt 1 — Create the application project

```text
Create a new BW application project named Retail_Order_Logger.
```

## Prompt 2 — Create the main process

```text
Create a Process
Name: OrderProcess
Location: retail_order_logger package
Add the following activities in sequence and link them:
Timer: To initiate the process
Log: To log the start of order processing
Mapper: To map retail order details
Log: To log mapped order information
CallProcess: To call the order validation subprocess
Log: To log the end of the process
Link all activities.
```

## Prompt 3 — Create the validation subprocess

```text
Create a Subprocess
Name: ValidateOrder
Location: retail_order_logger package
Add the following activities and link them:
Start
Log: Add Log after Start activity
Log1: Add Log1 after Log activity
End
Link all activities.
```

## Prompt 4 — Add schemas and resources

> **Before running:** replace `<PATH_TO_RetailOrderSchema.xsd>` with the path to the schema file on your own machine.
> Example: `C:\Retail\TestData\RetailOrderSchema.xsd` (Windows) or `/Users/you/retail/RetailOrderSchema.xsd` (macOS/Linux).

```text
Schemas and Resources
Copy schema from:
 <PATH_TO_RetailOrderSchema.xsd>
```

## Prompt 5 — Define module properties

```text
Module Properties
Create the following module properties as per their type:
Name: orderStoreId, Type: Long, Value: 10001
Name: defaultOrderId, Type: Integer, Value: 501
Name: enableOrderValidation, Type: Boolean, Value: true
Name: orderApiPassword, Type: Password, Value: Retail@123
Create a new group retailGroup with:
Name: storeName
Type: String
Value: RetailMart
```

## Prompt 6 — Configure activities in the main process

```text
Configure Activities from Main Process OrderProcess.bwp
For Log activity, configure input element message with value:
$Timer/Time
For Mapper activity, configure schema RetailOrderSchema.xsd. After schema configuration, configure the input elements as:
orderName
with value:
$_processContext/ApplicationName
orderId
with value:
xsd:integer(bw:getModuleProperty("defaultOrderId"))
For Log1, configure input element message with value:
$Mapper/tns:orderName
For CallProcess, configure attribute Process Name with value:
ValidateOrder.bwp
For Log2, map input element message with value:
bw:getModuleProperty("orderApiPassword")
```

## Prompt 7 — Configure activities in the subprocess

```text
Configure Activities from Subprocess ValidateOrder.bwp
For Log, map input element message with value:
bw:getModuleProperty("BW.PROCESS.NAME")
For Log1, map input element message with value:
bw:getModuleProperty("/retailGroup/storeName")
```

## Alternatively — paste all prompts in one go

Prefer to run it as a single prompt? Copy the complete block below into your AI assistant instead of pasting each prompt individually. Remember to replace the `<...>` placeholder(s) with paths on your own machine first.

```text
Basic Retail Order Logger
Create a new BW application project named Retail_Order_Logger. Within this project, perform the following tasks:
1. Create a Process
Name: OrderProcess
Location: retail_order_logger package
Add the following activities in sequence and link them:
Timer: To initiate the process
Log: To log the start of order processing
Mapper: To map retail order details
Log: To log mapped order information
CallProcess: To call the order validation subprocess
Log: To log the end of the process
Link all activities.
2. Create a Subprocess
Name: ValidateOrder
Location: retail_order_logger package
Add the following activities and link them:
Start
Log: Add Log after Start activity
Log1: Add Log1 after Log activity
End
Link all activities.
3. Schemas and Resources
Copy schema from:
 <PATH_TO_RetailOrderSchema.xsd>
4. Module Properties
Create the following module properties as per their type:
Name: orderStoreId, Type: Long, Value: 10001
Name: defaultOrderId, Type: Integer, Value: 501
Name: enableOrderValidation, Type: Boolean, Value: true
Name: orderApiPassword, Type: Password, Value: Retail@123
Create a new group retailGroup with:
Name: storeName
Type: String
Value: RetailMart
5. Configure Activities from Main Process OrderProcess.bwp
For Log activity, configure input element message with value:
$Timer/Time
For Mapper activity, configure schema RetailOrderSchema.xsd. After schema configuration, configure the input elements as:
orderName
with value:
$_processContext/ApplicationName
orderId
with value:
xsd:integer(bw:getModuleProperty("defaultOrderId"))
For Log1, configure input element message with value:
$Mapper/tns:orderName
For CallProcess, configure attribute Process Name with value:
ValidateOrder.bwp
For Log2, map input element message with value:
bw:getModuleProperty("orderApiPassword")
6. Configure Activities from Subprocess ValidateOrder.bwp
For Log, map input element message with value:
bw:getModuleProperty("BW.PROCESS.NAME")
For Log1, map input element message with value:
bw:getModuleProperty("/retailGroup/storeName")
```
