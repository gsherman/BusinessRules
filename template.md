# Business Rule Template

This template is helpful when defining new business rules. 
It can be provided to business users, who can fill out the template and submit it to the technical staff.

Like any business process template, this is meant to be used as a guide, and as a starting point. Often, additonal discussions betwen business users and technical staff to further refine the rule may be useful. 


## Description of the rule.  

Be as descriptive as possible.  Use your own words. Talk like a human - not a robot, computer, or geek! 

<textarea rows="6" cols="80"></textarea>

## Which object types does this rule apply to?

<label><input type="checkbox">Case</label>  
<label><input type="checkbox">Subcase</label>  
<label><input type="checkbox">Solution</label>  
<label><input type="checkbox">Change Request</label>  
<label><input type="checkbox">Part Request</label>  
<label><input type="checkbox">Action Item</label>  
<label><input type="checkbox">Contact</label>  
<label><input type="checkbox">Other</label>  

## What action or event should trigger the rule to start?

Examples:
* Start this rule when a case is dispatched to a queue
* Start this rule when a case is closed
* Start this rule when a new customer (contact) is created

<textarea rows="6" cols="80"></textarea>

## What action or event should trigger the rule to stop?

Examples:
* Stop this rule when the case is accepted or yanked from a queue
* Stop this rule when the subcase is closed

<textarea rows="6" cols="80"></textarea>

## Describe any conditions that apply to this rule.

Examples:
* This rule should only fire if the Case Type is Benefits
* This rule should only fire if the Queue is Technical Support
* This rule should only fire if the Contact is not in the United States

<textarea rows="6" cols="80"></textarea>

---

## Business Rule Actions


Business rules have associated Actions. The Action is *what* happens when the rule fires. A business rule must have at least one action, and it can have as many actions as needed.

---

## Action #1

### When should this action start?

Examples:
* Start this action immediately 
* Start this action if the case has been sitting in the queue for more than 4 hours
* Start this action 4 hours before the subcase is due

<textarea rows="6" cols="80"></textarea>

### Which calendar should be used?

<label><input type="radio" name="calendar1">Elapsed Time</label>  
<label><input type="radio" name="calendar1">Support Business Hours</label>  
<label><input type="radio" name="calendar1">Customer Business Hours</label>  



### What action should happen when the rule fires?

<label><input type="radio" name="action1">Notify people via a message (Email, In-app Notifications, SMS, etc.). This is the most common action.</label>  
<label><input type="radio" name="action1">Execute an external script or executable</label>  
<label><input type="radio" name="action1">Send a message to Dovetail Carrier</label>  

### Notification Message

If the action is to notify people:
Who should get notified?
This could be specific people, such as Fred, the Support Manager. Or it could be relative to the object that the rule fires for, such as the Case Owner, or the Current Queue Members. You can use a combination of both. 

#### Notify Specific People:

<textarea rows="4" cols="80"></textarea>



#### Notify People relative to the object:

<label><input type="checkbox">Current Owner</label>  
<label><input type="checkbox">Current Owner’s Supervisor</label>  
<label><input type="checkbox">Contact</label>  
<label><input type="checkbox">Current Queue Members</label>  
<label><input type="checkbox">Originator</label>  
<label><input type="checkbox">Yanked From User</label>  
<label><input type="checkbox">Originator/Creator</label>  
<label><input type="checkbox">Parent Case Owner (for child cases or subcases)</label>


### What should the notification message say?

<textarea rows="8" cols="80"></textarea>


### How important is this message?

<label><input type="radio" name="urgency1">Low</label>  
<label><input type="radio" name="urgency1">Medium</label>  
<label><input type="radio" name="urgency1">High</label>


### Execute an external script or executable
If the action is to execute a script or executable, what is the external script or executable that should be executed?

<textarea rows="6" cols="80"></textarea>

### Send a message to Dovetail Carrier
If the action is to send a message to Dovetail Carrier, what is the message that should be sent?

<textarea rows="6" cols="80"></textarea>



### Repeating Action

Should this action repeat?

<label><input type="radio" name="repeat1">No</label>  
<label><input type="radio" name="repeat1">Yes</label>


A repeating action should have a stop event. 
Example: Notify queue members when a case is dispatched to a queue. Keep notifying them every 4 hours until the case is accepted out of the queue.

### If this action should repeat, how often should it repeat? 
Example: Repeat every 4 hours, or every 30 days

<textarea rows="4" cols="80"></textarea>

### How long should it keep repeating for?
Example: Repeat every 4 hours, *for the next 24 hours*

<textarea rows="4" cols="80"></textarea>


---

## Action #2

### When should this action start?

Examples:
* Start this action immediately 
* Start this action if the case has been sitting in the queue for more than 4 hours
* Start this action 4 hours before the subcase is due

<textarea rows="6" cols="80"></textarea>

### Which calendar should be used?

<label><input type="radio" name="calendar2">Elapsed Time</label>  
<label><input type="radio" name="calendar2">Support Business Hours</label>  
<label><input type="radio" name="calendar2">Customer Business Hours</label>  



### What action should happen when the rule fires?

<label><input type="radio" name="action2">Notify people via a message (Email, In-app Notifications, SMS, etc.). This is the most common action.</label>  
<label><input type="radio" name="action2">Execute an external script or executable</label>  
<label><input type="radio" name="action2">Send a message to Dovetail Carrier</label>  

### Notification Message

If the action is to notify people:
Who should get notified?
This could be specific people, such as Fred, the Support Manager. Or it could be relative to the object that the rule fires for, such as the Case Owner, or the Current Queue Members. You can use a combination of both. 

#### Notify Specific People:

<textarea rows="4" cols="80"></textarea>



#### Notify People relative to the object:

<label><input type="checkbox">Current Owner</label>  
<label><input type="checkbox">Current Owner’s Supervisor</label>  
<label><input type="checkbox">Contact</label>  
<label><input type="checkbox">Current Queue Members</label>  
<label><input type="checkbox">Originator</label>  
<label><input type="checkbox">Yanked From User</label>  
<label><input type="checkbox">Originator/Creator</label>  
<label><input type="checkbox">Parent Case Owner (for child cases or subcases)</label>


### What should the notification message say?

<textarea rows="8" cols="80"></textarea>


### How important is this message?

<label><input type="radio" name="urgency2">Low</label>  
<label><input type="radio" name="urgency2">Medium</label>  
<label><input type="radio" name="urgency2">High</label>


### Execute an external script or executable
If the action is to execute a script or executable, what is the external script or executable that should be executed?

<textarea rows="6" cols="80"></textarea>

### Send a message to Dovetail Carrier
If the action is to send a message to Dovetail Carrier, what is the message that should be sent?

<textarea rows="6" cols="80"></textarea>



### Repeating Action

Should this action repeat?

<label><input type="radio" name="repeat2">No</label>  
<label><input type="radio" name="repeat2">Yes</label>


A repeating action should have a stop event. 
Example: Notify queue members when a case is dispatched to a queue. Keep notifying them every 4 hours until the case is accepted out of the queue.

### If this action should repeat, how often should it repeat? 
Example: Repeat every 4 hours, or every 30 days

<textarea rows="4" cols="80"></textarea>

### How long should it keep repeating for?
Example: Repeat every 4 hours, *for the next 24 hours*

<textarea rows="4" cols="80"></textarea>


---

If your business rule needs more than 2 actions, simply include additional actions that follow the same pattern as above


