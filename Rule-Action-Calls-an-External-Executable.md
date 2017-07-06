Rule Action Calls an External Executable

Example of executables include your own custom exe, cbbatch.exe, powershell.exe, cscript.exe, etc.

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |Rule Action Calls an External Executable|
| Object Type  | Case|
| Start Events| Log Note (or whatever event you want)

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Call an External Executable
| Action Type	| Command Line
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
c:\path_to_exe\my-executable.exe Param1 Param2 [Param3 Rule Property] [Param4 Rule Property]
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager

## Notes
* Take note of the Rule Action Type of `Command Line`
* If your executable has any dependencies (DLLs, config files, etc.), then they  should be in the same directory as your executable
* If you need to make sure that your executable is started from a certain directory, then a wrapper script may be useful. This could be a `.BAT` file, `.SH` shell script, or a `.PS1` PowerShell script.
The wrapper script could change (`cd`) to the correct directory

## Related
* [Rule Action calls cbbatch scripts](Rule-Action-calls-cbbatch-scripts)
