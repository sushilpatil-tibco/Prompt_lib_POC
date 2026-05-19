# SOAP-Retail_Loyalty_Service

> Copy this prompt into your AI assistant to generate or guide a TIBCO BW6 implementation.

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
