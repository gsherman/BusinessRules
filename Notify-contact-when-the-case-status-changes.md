## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify contact when the case status changes|
| Object Type  | Case  |
| Start Events| Change Status
| Condition 1| Logger != dovetail-selfservice

## Rule Action #1
|  |  |
| ------------- | ------------- |
| Title	| Notify the Contact
| Action Type	| Message
| To |	[Contact]
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
RE: The status of your [Object Type] has changed to [Status]

[Contact First Name],
The status of your [Object Type] has changed to [Status].

You are being notified because you are the primary contact for the [Object Type].

Case ID: [Object ID]
Case Title: [Title]

[You can view your case within our SelfService portal]([DovetailSelfServiceURL]/cases/show/[Object ID]) 

```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
