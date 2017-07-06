## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify customers of a public note|
| Object Type  | Case  |
| Start Events| Log Note
| Condition 1 | Logger does not start with dovetail
| Condition 2 | Notes Log Is Internal = 0

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
RE: About Case [Object ID] : [Title]

[Contact First Name],

We have updated your case. 
Please [click here]([DovetailSelfServiceURL]/cases/show/[Object ID]) to be taken to our online portal to see the message.
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
