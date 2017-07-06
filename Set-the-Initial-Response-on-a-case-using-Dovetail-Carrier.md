When an Agent logs an email or logs a phone call to a case, mark the Initial Response flag on the case to True. 

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Set the Initial Response on a case automatically using Carrier  |
| Object Type  | Case  |
| Start Events| Log Email, Phone Log
| Condition 1 | Responded To = 0
| Condition 2 |Logger != Carrier
| Condition 3 |Logger != SelfService

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Set the Initial Response Flag
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=CallToolkit
toolkit=Support
method=InitialResponse
caseIDNum=[Case ID]
UserName=[Logger]
```
Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager)
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Rule Properties
The following rule properties are used by this rule and may need to be added to your system. 
* [Responded To](Responded-To-Rule-Property)
* [Case ID](Case-ID-Rule-Property)

## Notes
The conditions exclude events that happen via Dovetail Carrier (such as an incoming email on a case), and they exclude events that happen from within SelfService/WebSupport. You may need to adjust these Logger conditions to match the login names used in your specific environment. 


