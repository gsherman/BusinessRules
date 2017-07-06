## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify a user when a case is yanked from them  |
| Object Type  | Case  |
| Start Events| Yank
| Conditions | None

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Notify the Yankee
| Action Type	| Message
| To |	[Yanked From User]
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
RE: [Object Type] [Object ID] was yanked from you by [Logger]
[Object Type] [Object ID] was yanked from you by [Logger].
Case Title:  [Title]
Customer: [Contact First Name] [Contact Last Name] at [Site Name]

[DovetailAgentURL]/support/cases/[Object ID]
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager

## Rule Properties
The following rule properties are used by this rule and may need to be added to your system. 
* [Yanked From User](Yanked-From-User-Rule-Property)
