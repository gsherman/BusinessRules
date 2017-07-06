## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | When the parent case is closed, close all the children |
| Object Type  | Case  |
| Start Events| Close Task
| Condition 1 | Number Of Child Cases > 0

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Auto-Close the Children
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=CloseChildCases
caseID=[Case ID]
Status=Closed
Resolution=Auto-Closed
Summary=Automatically closed via business rule
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) 
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Rule Properties
The following rule properties are used by this rule and may need to be added to your system. 
* [Case ID](Case-ID-Rule-Property)
* [Number Of Child Cases](Number-Of-Child-Cases-Rule-Property)

## Notes
When this message is handled, an internal note will be logged to the parent case with details of what happened, including which cases were closed, which are already closed, and which could not e closed (along with the reason why it could not be closed). 

### Example of note that is logged

```
Closing all child cases…
Case 4222 - closed
Case 4268 - closed
Case 4267 - already closed
Case 4268 - not closed. This case has open general subcases, therefore it cannot be closed. 
---
Closed: 2
Already Closed: 1
Not Closed: 1
```
