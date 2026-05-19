# REST-Retail_Product_Service

> Copy this prompt into your AI assistant to generate or guide a TIBCO BW6 implementation.

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
