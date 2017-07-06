## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Notify the owner of a case if a log is performed by someone else  |
| Object Type  | Case  |
| Start Events| Log Email, Phone Log, Close Task, Email In, Log Note, Log Research
| Condition 1 |Logger != [Current Owner]
| Condition 2 |Current Owner does not start with dovetail

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Notify the Owner
| Action Type	| Command Line
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True
| To | Current Owner

### Rule Action Message	
```
RE: [Object Type] [Object ID] has been updated

[Object Type] [Object ID] has been updated by [Logger]. 
Case Title:  [Title]
Customer: [Contact First Name] [Contact Last Name] at [Site Name]
Activity: [Activity Name]
Details:

[Email Log Notes][Phone Notes][Notes Text][Close Case Notes]

-----------------------------------------------------------------------------------

View this [Object Type] in Dovetail Agent:
[DovetailAgentURL]/support/cases/[Object ID]

```

### Requires:

* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager


## Rule Properties
The following rule properties are used by this rule and may need to be added to your system. 
* [Case ID](Case-ID-Rule-Property)
* Email Log Notes
* Phone Notes
* Notes Text
* Close Case Notes
* [DovetailAgentURL](DovetailAgentURL-Rule-Property)


