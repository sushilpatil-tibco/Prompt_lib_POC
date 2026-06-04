# REST - Retail Product Service

> Copy these prompts into your AI assistant to generate or guide a TIBCO BW6 implementation.

## Overview

A REST product API exposing GET and POST operations, backed by a BW process with Swagger documentation. Paste the prompts into your AI assistant **one at a time, in order**, and review the generated output in TIBCO Business Studio for BusinessWorks before moving on.

| Prompt | What it does |
|---|---|
| Prompt 1 | Create the BW application |
| Prompt 2 | Create the REST service and operations |
| Prompt 3 | Create the product schema |
| Prompt 4 | Create the process and activities |
| Prompt 5 | Configure operations, logging, and Swagger |

## Prompt 1 — Create the application

```text
Create a new BW application project named "Retail_Product_Service".
```

## Prompt 2 — Create the REST service and operations

```text
Create REST service named:
ProductService
Create the following operations:
GET Product
POST Product
```

## Prompt 3 — Create the product schema

```text
Create schema:
Product.xsd
Product schema fields:
productId : integer
productName : string
productPrice : decimal
category : string
```

## Prompt 4 — Create the process and activities

```text
Create process:
Name: ProductAPIProcess
Add and configure activities:
Receive HTTP Request
Mapper
Log
Send HTTP Response
```

## Prompt 5 — Configure operations, logging, and Swagger

```text
Configure GET operation:
Return sample product details
Configure POST operation:
Accept product information
Log received product name
Configure Log activity:
Message =
 concat("Retail product request:",$productName)
Enable Swagger documentation for the REST service.
```

## Alternatively — paste all prompts in one go

Prefer to run it as a single prompt? Copy the complete block below into your AI assistant instead of pasting each prompt individually.

```text
REST-Retail_Product_Service
Create a new BW application project named "Retail_Product_Service".
Create REST service named:
ProductService
Create the following operations:
GET Product
POST Product
Create schema:
Product.xsd
Product schema fields:
productId : integer
productName : string
productPrice : decimal
category : string
Create process:
Name: ProductAPIProcess
Add and configure activities:
Receive HTTP Request
Mapper
Log
Send HTTP Response
Configure GET operation:
Return sample product details
Configure POST operation:
Accept product information
Log received product name
Configure Log activity:
Message =
 concat("Retail product request:",$productName)
Enable Swagger documentation for the REST service.
```
