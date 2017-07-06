
## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | auto-close case if no reply from customer |
| Object Type  | Case  |
| Start Events| Change Status
| Cancel Events | Change Status, Close Task
| Condition 1 | Status= `Awaiting Customer Response (Auto-Close)`

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Notify contact
| Action Type	| Message
| Start Action	| 3 days from Event Creation using Elapsed Time
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
RE: About case [Case ID] (  [Title] )
Hello [Contact First Name],
A few days ago, our support staff replied to your recent support case.
Case Number: [Case ID]
Case Title: [Title]
Since then, we have not received any response back from you, and would like to know if you consider this issue to be closed. If you have any further questions, please use our SelfService site to leave us a note.
Your case is available on our SelfService site at:
http://support.company.com/selfservice/case/[Case ID Number]
This issue will be automatically closed in 3 days if you choose not to respond.
Sincerely,
Dovetail Support team
```

## Rule Action #2

|  |  |
| ------------- | ------------- |
| Title	| Close the Case
| Action Type	| Carrier Message
| Start Action	| 6 days from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=calltoolkit
toolkit=Support
method=CloseCase
caseIDNum=[Case ID]
Resolution=Auto-Closed
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager) or Clarify Rulemanager
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Rule Properties
The following rule properties are used by this rule and may need to be added to your system. 
* [Case ID](Case-ID-Rule-Property)

## Notes
* The contact will be notified 3 days after the agent sets the status to `Awaiting Customer Response (Auto-Close)`
* The case will be automatically closed 3 days after that (6 days total from when the agent set the status)
* The rule will be canceled if the status gets changed or the case gets closed.

More details on this workflow can be found at http://clarify.dovetailsoftware.com/gsherman/2011/01/06/auto-closing-a-case-workflow/

### Option:  Use a PowerShell or ClearBasic script
The rule action uses Dovetail Carrier's SDK Toolkit extension to close the case. 
If you don't have Dovetail Carrier, another option here is to use a `cbbatch` script, written in ClearBasic.  
Or, use a PowerShell script that uses the Dovetail SDK, such  as [CloseCase.ps1](https://github.com/gsherman/powershell)
This will work just as well. 

