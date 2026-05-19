# SubProcess-Retail_Returns

> Copy this prompt into your AI assistant to generate or guide a TIBCO BW6 implementation.

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
