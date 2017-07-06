## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |SLA: violation|
| Object Type  | Case|
| Start Events| Next Action Due Date Calculated
| Cancel Events | Close Task, Next Action Due Date Calculated

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Next Action Due Date Calculated
| Action Type	| Message
| Start Action	| 0 minutes from Next Action Due Date
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True
| To | Current Owner

### Rule Action Message	
```
RE: SLA Violation: About Case [Object ID] : [Title]
Case [Object ID] has violated its SLA

Title: [Title]
Severity: [Severity]
Customer: [Contact First Name] [Contact Last Name] at [Site Name]
Next Action: [Next Action]
Next Action Due Date: [Next Action Due Date]
Owner: [Current Owner]

[DovetailAgentURL]/support/cases/[Object ID]
```


## Rule Action #2

|  |  |
| ------------- | ------------- |
| Title	| IncrementNumberOfSlaViolations
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=IncrementNumberOfSlaViolations
CaseID=[Case ID]
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager)
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Notes
* For more details on SLAs with Dovetail Carrier, refer to (this blog post](http://clarify.dovetailsoftware.com/gsherman/2016/08/09/sla-calculations-using-dovetail-carrier/)

