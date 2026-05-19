# Basic Retail Order Logger

> Copy this prompt into your AI assistant to generate or guide a TIBCO BW6 implementation.

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
 C:\Retail\TestData\RetailOrderSchema.xsd
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
