Rule Action calls cbbatch (ClearBasic Batch) scripts

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |Rule Action calls cbbatch scripts|
| Object Type  | Case|
| Start Events| Log Note (or whatever event you want)

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Call cbbatch scripts
| Action Type	| Command Line
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
cbbatch.bat -f "MyCBBatchScript.cbs" -r StartingSubRoutine
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager

## Notes
* Take note of the Rule Action Type of `Command Line`

## Strategy
Rather than hard-coding a bunch of paths within business rule actions, I like to keep things simple.

Notice that the rule action is simply calling `cbbatch.bat`, without any paths. 

I like to put cbbatch.exe and all of its dependent DLLs into a single directory, such as `C:\bin\cbbatch`
Then, I put all of my cbbatch scripts into a single directory, such as `C:\bin\cbbatch\scripts`

I also make sure that the cbbatch directory is included in the system path. 

Then my rule action calls `cbbatch.bat`. This bat file wrapper changes to the scripts directory, and then calls cbbatch.exe, passing through all of the input params. See below for my example `cbbatch.bat` script.

All of this keeps things organized, and eliminates hard-coded paths within business rules. 

## Alternative Strategy
Another option is to use [Configuration Item Rule Properties](https://support.dovetailsoftware.com/documentation/RuleManager/2.4.2/html/3936.htm) for cbbatch.exe and/or the path to your script.

For example, the Rule Action Message could look like this:
```
[cbbatch] -f "MyCBBatchScript.cbs" -r StartingSubRoutine
```

With the `[cbbatch]` rule property could be defined as `[ConfigItem.cbbatch.String]`

and the cbbatch config item could be defined as `c:\bin\cbbatch\cbbatch.bat`


## cbbatch.bat
```
@echo off
cd c:\bin\cbbatch\scripts
c:\bin\cbbatch\cbbatch.exe %* 
```

