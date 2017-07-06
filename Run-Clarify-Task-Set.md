Have rulemanager run a clarify task set using Clarify's tskmgr.exe

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |Run Clarify Task Set|
| Object Type  | Case|
| Start Events| Run Task Set

## Rule Action #1
|  |  |
| ------------- | ------------- |
| Title	| Run Clarify Task Set
| Action Type	| Command Line
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
C:\clarify\11.5\Server\rulemgr\tskmgr.exe Case id_number "[Object ID]" "[Task Set Name]"
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager

## Rule Properties
* [Task Set Name](https://github.com/gsherman/BusinessRuleRecipes/wiki/Task-Set-Name-Rule-Property)


