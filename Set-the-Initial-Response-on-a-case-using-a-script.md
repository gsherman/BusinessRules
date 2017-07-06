When an Agent logs an email or logs a phone call to a case, mark the Initial Response flag on the case to True. 

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Set the Initial Response on a case automatically using Carrier  |
| Object Type  | Case  |
| Start Events| Log Email, Phone Log
| Condition 1 | Responded To = 0
| Condition 2 |Logger != Carrier
| Condition 3 |Logger != SelfService

## Rule Action #1
|  |  |
| ------------- | ------------- |
| Title	| Set the Initial Response Flag
| Action Type	| Command Line
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
C:\Dovetail\custom\RuleManagerActions\InitialResponse\InitialResponse.bat [Case ID], [Logger]
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
* [Dovetail SDK](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20SDK)
* [Set Initial Response Scripts](https://github.com/gsherman/powershell)

## Rule Properties
The following rule properties are used by this rule and may need to be added to your system. 
* [Responded To](https://github.com/gsherman/BusinessRuleRecipes/wiki/Responded-To-Rule-Property)
* [Case ID](https://github.com/gsherman/BusinessRuleRecipes/wiki/Case-ID-Rule-Property)

## Notes
The conditions exclude events that happen via Dovetail Carrier (such as an incoming email on a case), and they exclude events that happen from within SelfService/WebSupport. You may need to adjust these Logger conditions to match the login names used in your specific environment. 

### Option:  Use cbbatch and a ClearBasic script
The rule action calls a script to set the initial response. In this specific example, it's calling into a PowerShell script that uses the Dovetail SDK. 
If you don't have the Dovetail SDK, another option here is to use a `cbbatch` script, written in ClearBasic.  
This will work just as well. 
