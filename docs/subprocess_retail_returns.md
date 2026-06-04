# SubProcess - Retail Returns

> Copy these prompts into your AI assistant to generate or guide a TIBCO BW6 implementation.

## Overview

A main process that calls a validation subprocess to handle retail returns. Paste the prompts into your AI assistant **one at a time, in order**, and review the generated output in TIBCO Business Studio for BusinessWorks before moving on.

| Prompt | What it does |
|---|---|
| Prompt 1 | Create the BW application |
| Prompt 2 | Create the main process and subprocess |
| Prompt 3 | Add the activities |
| Prompt 4 | Configure the main process and subprocess |

## Prompt 1 — Create the application

```text
Create a new BW application named "Retail_Return_Process".
```

## Prompt 2 — Create the main process and subprocess

```text
Create main process:
Name: ReturnMainProcess
Create subprocess:
Name: ValidateReturn
```

## Prompt 3 — Add the activities

```text
Main process activities:
Timer
Log
Call Process
Log
Subprocess activities:
Start
Mapper
Log
End
```

## Prompt 4 — Configure the main process and subprocess

```text
Configure main process:
Log1 message = "Retail return initiated"
Call subprocess = ValidateReturn.bwp
Log2 message = "Retail return completed"
Configure subprocess:
customerId = "CUST1001"
returnStatus = "Approved"
Configure subprocess Log:
Message = "$returnStatus"
```

## Alternatively — paste all prompts in one go

Prefer to run it as a single prompt? Copy the complete block below into your AI assistant instead of pasting each prompt individually.

```text
SubProcess-Retail_Returns
Create a new BW application named "Retail_Return_Process".
Create main process:
Name: ReturnMainProcess
Create subprocess:
Name: ValidateReturn
Main process activities:
Timer
Log
Call Process
Log
Subprocess activities:
Start
Mapper
Log
End
Configure main process:
Log1 message = "Retail return initiated"
Call subprocess = ValidateReturn.bwp
Log2 message = "Retail return completed"
Configure subprocess:
customerId = "CUST1001"
returnStatus = "Approved"
Configure subprocess Log:
Message = "$returnStatus"
```
