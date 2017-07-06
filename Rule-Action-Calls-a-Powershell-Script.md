Rule Action Calls a Powershell Script

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |Rule Action Calls a Powershell Script|
| Object Type  | Case|
| Start Events| Log Note (or whatever event you want)

## Rule Action #1
|  |  |
| ------------- | ------------- |
| Title	| Call a powershell script
| Action Type	| Command Line
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
C:\powershell\closecase.bat [Object ID] 
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager

## Notes
* Take note of the Rule Action Type of `Command Line`
* In this example, `CloseCase.bat` is simply a wrapper script for calling the `CloseCase.ps1` Powershell script.
* All of these scripts are freely available at https://github.com/gsherman/powershell

## Related
* [Rule Action calls an external executable](Rule-Action-Calls-an-External-Executable)
