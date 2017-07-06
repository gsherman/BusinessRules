Changes Case Status from Customer Update to Wait Response when an Agent responds to a customer

This rule is often used in conjunction with the [Changes Case Status to Customer Update](Changes-Case-Status-to-Customer-Update) rule, so that status changes happen automatically, depending on whether an Agent responded to a customer or whether the customer responded to the Support center. 

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Changes Case Status to Waiting Response when an Agent responds to a Case  |
| Object Type  | Case  |
| Start Events| Log Email, Phone Log
| Condition 1 | Status = Customer Update
| Condition 2 |Logger does not start with dovetail

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Change Status
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
Type=CallToolkit
Toolkit=Support
Method=ChangeCaseStatus
CaseIdNum=[Object ID]
NewStatus=Wait Response
Notes=Case has been updated by Dovetail
```
Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager)
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Notes
The conditions excludes events that happen via a Dovetail app (such as incoming email via Carrier, or notes logged via SelfService). You may need to adjust these Logger conditions to match the login names used in your specific environment. 


