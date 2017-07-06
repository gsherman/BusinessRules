## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify a user when a case is assigned to them |
| Object Type  | Case  |
| Start Events| Assign
| Conditions | None

## Rule Action #1
|  |  |
| ------------- | ------------- |
| Title	| Notify the Yankee
| Action Type	| Message
| To |	[Current Owner]
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
RE: [Object Type] [Object ID] Assigned
[Object Type] [Object ID] has been assigned to you by [Logger]. 

Case Title:  [Title]
Customer: [Contact First Name] [Contact Last Name] at [Site Name]

[DovetailAgentURL]/support/cases/[Object ID]
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
