# JMS - Retail Order Queue

> Copy these prompts into your AI assistant to generate or guide a TIBCO BW6 implementation.

## Overview

A queue-based process that receives retail orders from a TIBCO EMS queue, logs them, writes them to a file, and replies to the sender. Paste the prompts into your AI assistant **one at a time, in order**, and review the generated output in TIBCO Business Studio for BusinessWorks before moving on.

| Prompt | What it does |
|---|---|
| Prompt 1 | Create the BW application |
| Prompt 2 | Create the JNDI configuration |
| Prompt 3 | Create the JMS connection shared resource |
| Prompt 4 | Create module properties |
| Prompt 5 | Create the process and activities |
| Prompt 6 | Configure the activities |

## Prompt 1 — Create the application

```text
Create a new BW application named "Retail_Order_Queue".
```

## Prompt 2 — Create the JNDI configuration

> **Before running:** replace `<EMS_HOST>` and `<EMS_PORT>` with your TIBCO EMS server address.
> Example: `localhost` and `7222` (the local EMS default).

```text
Create JNDI configuration:
Provider: TIBCO EMS
Initial Context Factory:
 com.tibco.tibjms.naming.TibjmsInitialContextFactory
URL:
 tibjmsnaming://<EMS_HOST>:<EMS_PORT>
```

## Prompt 3 — Create the JMS connection shared resource

```text
Create JMS Connection shared resource:
Name: RetailJMSConnection
Messaging Style: Queue
JNDI Configuration:
 retail.jms.EMSConfig
```

## Prompt 4 — Create module properties

> **Before running:** replace `<PATH_TO_orders.log>` with the output log path on your own machine.
> Example: `C:\tmp\RetailOrders\orders.log` (Windows) or `/tmp/retail/orders.log` (macOS/Linux).

```text
Create module properties:
QUEUE_NAME : String : retail.orders.queue
OUTPUT_FILE : String : <PATH_TO_orders.log>
```

## Prompt 5 — Create the process and activities

```text
Create process:
Name: ReceiveRetailOrder
Add and link activities:
JMS Receive Message
Log
Write File
Reply to JMS Message
```

## Prompt 6 — Configure the activities

```text
Configure JMS Receive Message:
Destination = retail.orders.queue
Messaging Style = Queue
JMS Connection = RetailJMSConnection
Configure Log activity:
Message =
 concat("Retail order received:",$JMSReceiveMessage/Body)
Configure Write File:
Filename = $OUTPUT_FILE
Append = true
Create Non Existing Directories = true
Configure Reply to JMS Message:
Body = "Retail order processed successfully"
```

## Alternatively — paste all prompts in one go

Prefer to run it as a single prompt? Copy the complete block below into your AI assistant instead of pasting each prompt individually. Remember to replace the `<...>` placeholder(s) with values for your own environment first.

```text
JMS-Retail_Order_queue
Create a new BW application named "Retail_Order_Queue".
Create JNDI configuration:
Provider: TIBCO EMS
Initial Context Factory:
 com.tibco.tibjms.naming.TibjmsInitialContextFactory
URL:
 tibjmsnaming://<EMS_HOST>:<EMS_PORT>
Create JMS Connection shared resource:
Name: RetailJMSConnection
Messaging Style: Queue
JNDI Configuration:
 retail.jms.EMSConfig
Create module properties:
QUEUE_NAME : String : retail.orders.queue
OUTPUT_FILE : String : <PATH_TO_orders.log>
Create process:
Name: ReceiveRetailOrder
Add and link activities:
JMS Receive Message
Log
Write File
Reply to JMS Message
Configure JMS Receive Message:
Destination = retail.orders.queue
Messaging Style = Queue
JMS Connection = RetailJMSConnection
Configure Log activity:
Message =
 concat("Retail order received:",$JMSReceiveMessage/Body)
Configure Write File:
Filename = $OUTPUT_FILE
Append = true
Create Non Existing Directories = true
Configure Reply to JMS Message:
Body = "Retail order processed successfully"
```
