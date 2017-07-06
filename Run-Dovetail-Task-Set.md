Have rulemanager run a Dovetail task set using Dovetail Carrier

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |Run Dovetail Task Set|
| Object Type  | Case|
| Start Events| Run Task Set

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Run Clarify Task Set
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=RunTaskSet
caseId=[Object ID]
taskSetName=[Task Set Name]
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) 
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Rule Properties
* [Task Set Name](Task-Set-Name-Rule-Property)


