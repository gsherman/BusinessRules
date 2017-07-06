
## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | When the last child case is closed, close the parent case.  |
| Object Type  | Case  |
| Start Events| Close Task
| Condition 1 | NumberOfOpenChildCasesOnParent = 0
| Condition 2 | Parent Case ID > 0

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
caseIDNum=[Parent Case ID]
Resolution=Auto-Closed
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) 
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Rule Properties
The following rule properties are used by this rule and may need to be added to your system. 
* [Conditions of Sibling Subcases ](https://github.com/gsherman/BusinessRuleRecipes/wiki/Conditions-of-Sibling-Subcases-Rule-Property)
* [Case ID](https://github.com/gsherman/BusinessRuleRecipes/wiki/Case-ID-Rule-Property)
* [NumberOfOpenChildCasesOnParent](https://github.com/gsherman/BusinessRuleRecipes/wiki/NumberOfOpenChildCasesOnParent)


### Option:  Use a PowerShell or ClearBasic script
The rule action uses Dovetail Carrier's SDK Toolkit extension to close the case. 
If you don't have Dovetail Carrier, another option here is to use a `cbbatch` script, written in ClearBasic.  
Or, use a PowerShell script that uses the Dovetail SDK, such  as [CloseCase.ps1](https://github.com/gsherman/powershell)
This will work just as well. 