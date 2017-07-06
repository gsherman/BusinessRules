## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify case owner when subcase closed|
| Object Type  | Subcase  |
| Start Events| Close Task
| Conditions | None

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Notify the Case Owner
| Action Type	| Message
| To |	[Parent Owner]
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
RE: [Object Type] [Object ID] was closed by [Logger]

[Object Type] [Object ID] was closed by [Logger]

You are being notified because you are the owner of the case.

Subcase that was closed:
[DovetailAgentURL]/support/subcases/[Object ID]
Parent Case:
[DovetailAgentURL]/support/cases/[Parent ID]

```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
