When a new solution is created, this rule will post the case to a [Hipchat](https://www.hipchat.com/) room. 
We'll delay the rule by 1 hour, in order to give the Solution Creator time to do some editing before its shared. 

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |Solution created - post to Hipchat|
| Object Type  | Solution|
| Start Events| Create

## Rule Action #1
|  |  |
| ------------- | ------------- |
| Title	| Post to Hipchat
| Action Type	| Command Line
| Start Action	| 1 hour from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
C:\hipchat\hipchat-message.bat "support-room" "[Object Type] [Object ID] has been created by [Logger]. : [DovetailAgentURL]/support/solutions/[Object ID] "
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager

## Notes
* This is an integration with [Hipchat](https://www.hipchat.com/), so you need a Hipchat account.
* This is using a `Command Line` action. The command line action calls out to a BAT file. The BAT file uses [curl](https://curl.haxx.se) to make a web request to hipchat. An example of `hipchat-message.bat` can be found [here](https://gist.github.com/gsherman/912d0ffe8738153020a7)

