## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |SLA: CalculateNextDueDate when status changed from ON HOLD|
| Object Type  | Case|
| Start Events| Change Status
| Condition 1 | Previous Status = On Hold

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| ClearNextDueDate
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=CalculateNextDueDate
ActEntryObjid=[Activity Objid]
CaseID=[Object ID]
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager)
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Notes
* For more details on SLAs with Dovetail Carrier, refer to [this blog post](http://clarify.dovetailsoftware.com/gsherman/2016/08/09/sla-calculations-using-dovetail-carrier/)

