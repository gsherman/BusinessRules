
Description

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Close parent case when all subcases are closed  |
| Object Type  | Subcase  |
| Start Events| Close Task
| Condition 1 | Conditions of Sibling Subcases does not contain Open

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Close Case
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=calltoolkit
toolkit=Support
method=CloseCase
caseIDNum=[Parent ID]
Resolution=Auto-Closed
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) 
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Rule Properties
The following rule properties are used by this rule and may need to be added to your system. 
* [Conditions of Sibling Subcases ](Conditions-of-Sibling-Subcases-Rule-Property)
* [Case ID](Case-ID-Rule-Property)

## Notes
More details on this workflow can be found at http://clarify.dovetailsoftware.com/gsherman/2013/08/05/how-to-close-a-case-when-all-of-its-subcases-are-closed/


### Option:  Use a PowerShell or ClearBasic script
The rule action uses Dovetail Carrier's SDK Toolkit extension to close the case. 
If you don't have Dovetail Carrier, another option here is to use a `cbbatch` script, written in ClearBasic.  
Or, use a PowerShell script that uses the Dovetail SDK, such  as [CloseCase.ps1](https://github.com/gsherman/powershell)
This will work just as well. 