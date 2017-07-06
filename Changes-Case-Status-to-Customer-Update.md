Changes Case Status to Customer Update when customer responds to a Case. 

This rule is often used in conjunction with the [Change Case Status to Wait Response](https://github.com/gsherman/BusinessRuleRecipes/wiki/Change-Case-Status-to-Wait-Response) rule, so that status changes happen automatically, depending on whether an Agent responded to a customer or whether the customer responded to the Support center. 

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Changes Case Status to Customer Update when customer responds to a Case  |
| Object Type  | Case  |
| Start Events| Email In, Log Note
| Condition 1 | Status != Customer Update
| Condition 2 |Logger starts with dovetail
| Condition 3 |Condition does not start with Closed

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
NewStatus="Customer Update"
Notes="Case has been updated by the Customer"
```
Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager)
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Notes
The conditions checks for events that happen via a Dovetail app (such as incoming email via Carrier, or notes logged via SelfService). You may need to adjust these Logger conditions to match the login names used in your specific environment. 


