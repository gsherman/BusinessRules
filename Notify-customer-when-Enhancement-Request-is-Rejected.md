## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify customer when Enhancement Request is Rejected|
| Object Type  | Case  |
| Start Events| Close Task
| Condition | Close Case Resolution = Enhancement Request Rejected
| Condition | Case Type = Enhancement Request

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
RE: About Case [Object ID] : [TITLE]
Hi [Contact First Name],

Thank you for contacting Dovetail Customer Support regarding [Title] (Case [Object ID])

Your enhancement request was considered carefully by product management, however on this occasion it was decided there was not a good fit within our current Dovetail Employee Engagement Suite.

We really appreciate your feedback and look forward to more ideas you have that will innovate and improve the product even further.

[You can view your case within our SelfService portal]([DovetailSelfServiceURL]/cases/show/[Object ID]) 

Kind regards,
Product Management Team
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
