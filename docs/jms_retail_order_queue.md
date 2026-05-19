# JMS-Retail_Order_queue

> Copy this prompt into your AI assistant to generate or guide a TIBCO BW6 implementation.

```text
JMS-Retail_Order_queue
Create a new BW application named "Retail_Order_Queue".
Create JNDI configuration:
Provider: TIBCO EMS
Initial Context Factory:
 com.tibco.tibjms.naming.TibjmsInitialContextFactory
URL:
 tibjmsnaming://localhost:7222
Create JMS Connection shared resource:
Name: RetailJMSConnection
Messaging Style: Queue
JNDI Configuration:
 retail.jms.EMSConfig
Create module properties:
QUEUE_NAME : String : retail.orders.queue
OUTPUT_FILE : String : C:\tmp\RetailOrders\orders.log
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
