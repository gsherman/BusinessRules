## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify customer when Enhancement Request is Accepted|
| Object Type  | Case  |
| Start Events| Close Task
| Condition 1| Close Case Resolution = Enhancement Request Accepted
| Condition 2| Case Type = Enhancement Request

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

Your enhancement request will be reviewed by our product management and considered for a future release.

[You can view your case within our SelfService portal]([DovetailSelfServiceURL]/cases/show/[Object ID]) 

We really appreciate your feedback and look forward to more ideas you have that will innovate the product even further.

Kind regards,
Product Management Team
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
