# SOAP - Retail Loyalty Service

> Copy these prompts into your AI assistant to generate or guide a TIBCO BW6 implementation.

## Overview

A SOAP service that returns customer loyalty points and tier, built from an imported WSDL. Paste the prompts into your AI assistant **one at a time, in order**, and review the generated output in TIBCO Business Studio for BusinessWorks before moving on.

| Prompt | What it does |
|---|---|
| Prompt 1 | Create the BW application |
| Prompt 2 | Import the WSDL and create the SOAP service |
| Prompt 3 | Create the process and activities |
| Prompt 4 | Configure the activities |

## Prompt 1 — Create the application

```text
Create a new BW application named "Retail_Loyalty_Service".
```

## Prompt 2 — Import the WSDL and create the SOAP service

```text
Import WSDL:
LoyaltyService.wsdl
Create SOAP service:
LoyaltyPointsService
```

## Prompt 3 — Create the process and activities

```text
Create process:
Name: LoyaltyProcess
Add activities:
SOAP Receive
Mapper
Log
SOAP Reply
```

## Prompt 4 — Configure the activities

```text
Mapper activity:
loyaltyPoints = 250
customerTier = "Gold"
Configure Log:
Message =
 concat("Retail loyalty request received for customer:",
 $customerId)
Configure SOAP Reply:
Return loyalty points response
```

## Alternatively — paste all prompts in one go

Prefer to run it as a single prompt? Copy the complete block below into your AI assistant instead of pasting each prompt individually.

```text
SOAP-Retail_Loyalty_Service
Create a new BW application named "Retail_Loyalty_Service".
Import WSDL:
LoyaltyService.wsdl
Create SOAP service:
LoyaltyPointsService
Create process:
Name: LoyaltyProcess
Add activities:
SOAP Receive
Mapper
Log
SOAP Reply
Mapper activity:
loyaltyPoints = 250
customerTier = "Gold"
Configure Log:
Message =
 concat("Retail loyalty request received for customer:",
 $customerId)
Configure SOAP Reply:
Return loyalty points response
```
