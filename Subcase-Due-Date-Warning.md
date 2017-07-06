## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify subcase owner before due date|
| Object Type  | Subcase  |
| Start Events| Create
| Conditions | None

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Notify the Subcase Owner
| Action Type	| Message
| To |	[Current Owner]
| Start Action	| -4 hours from Subcase Commit
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
RE: Subcase due date warning
You have a subcase whose due date is near.

Subcase ID: [Object ID]
Due Date:  [Commit Date-Time]
Title: [Subcase Title]

[DovetailAgentURL]/support/subcases/[Object ID]

```

Notes:
* Notice that the action 4 hours *before* the due date (`-4 hours`)

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
