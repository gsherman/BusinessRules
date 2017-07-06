## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify all queue members upon dispatch|
| Object Type  | Case  |
| Start Events| Dispatch, Forward
| Cancel Events | Accept, Yank, Forward
| Conditions | None

## Rule Action #1
|  |  |
| ------------- | ------------- |
| Title	| Notify the Queue Members
| Action Type	| Message
| To |		[Current Queue Members]
| Start Action	| 0 minutes from Event Creation using Support Business Hours
| Repeat Every	| 1 hour 
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
RE: [Object Type] [Object ID] Dispatched
[Object Type] [Object ID] has been dispatched to queue [Current Queue]. 

Case Title: [Title]

for [Contact First Name] [Contact Last Name] at [Site Name]

Priority: [Priority] 
Severity: [Severity]

[DovetailAgentURL]/support/cases/[Object ID]

```


## Rule Action #2
|  |  |
| ------------- | ------------- |
| Title	| Notify the Queue Supervisors after 2 hours
| Action Type	| Message
| To |		[Current Queue Supvsr]
| Start Action	| 2 hours from Event Creation using Support Business Hours
| Repeat Every	| 1 hour 
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
RE: [Object Type] [Object ID] Dispatched
[Object Type] [Object ID] has been dispatched to queue [Current Queue]. 

Case Title: [Title]

for [Contact First Name] [Contact Last Name] at [Site Name]

Priority: [Priority] 
Severity: [Severity]

[DovetailAgentURL]/support/cases/[Object ID]

```


Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
