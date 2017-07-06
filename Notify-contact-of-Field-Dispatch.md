## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify contact of Field Dispatch|
| Object Type  | Case  |
| Start Events| Dispatch Engineer
| Conditions | None

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
RE: Field Engineer scheduled
[Contact First Name],

A field engineer has been scheduled for your case
Case ID: [Object ID]
Case Title: [Title]
Scheduled Time: [Field Dispatch Requested Time]
Notes: [Field Dispatch Description]

```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
