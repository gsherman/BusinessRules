# Business Rule Template

<textarea></textarea>

<textarea>foo</textarea>

<input type="checkbox" name="vehicle" value="Bike">

This template is helpful when defining new business rules. 
It can be provided to business users, whi can fill out the template and submit it to the technical staff.

Like any business process template, this is meant to be used as a guide, and as a starting point. Often, additonal discussions betwen business users and technical staff to further refine the rule may be useful. 


## Description of the rule.  

Be as descriptive as possible.  Use your own words. Talk like a human, not a robot, computer, or geek! :wink:

&nbsp;

&nbsp;

&nbsp;

&nbsp;

## Which object types does this rule apply to?

* [ ] Case
* [ ] Subcase
* [ ] Solution
* [ ] Change Request
* [ ] Part Request
* [ ] Action Item
* [ ] Contact
* [ ] Other

## What action or event should trigger the rule to start?

Examples:
* Start this rule when a case is dispatched to a queue
* Start this rule when a case is closed
* Start this rule when a new customer (contact) is created

&nbsp;

&nbsp;

&nbsp;

&nbsp;

## What action or event should trigger the rule to stop?

Examples:
* Stop this rule when the case is accepted or yanked from a queue
* Stop this rule when the subcase is closed

&nbsp;

&nbsp;

&nbsp;

&nbsp;

## Describe any conditions that apply to this rule.

Examples:
* This rule should only fire if the Case Type is Benefits
* This rule should only fire if the Queue is Technical Support
* This rule should only fire if the Contact is not in the United States

&nbsp;

&nbsp;

&nbsp;

&nbsp;

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

&nbsp;

&nbsp;

&nbsp;

&nbsp;

### Which calendar should be used?

* [ ] Elapsed Time
* [ ] Support Business Hours
* [ ] Customer Business Hours


### What action should happen when the rule fires?
* [ ] Notify people via a message (Email, In-app Notifications, SMS, etc.). This is the most common action.
* [ ] Execute an external script or executable
* [ ] Send a message to Dovetail Carrier

### Notification Message

If the action is to notify people:
Who should get notified?
This could be specific people, such as Fred, the Support Manager. Or it could be relative to the object that the rule fires for, such as the Case Owner, or the Current Queue Members. You can use a combination of both. 

#### Specific People:

&nbsp;



#### People relative to the object:

* [ ] Current Owner
* [ ] Current Owner’s Supervisor
* [ ] Contact
* [ ] Current Queue Members
* [ ] Originator
* [ ] Yanked From User
* [ ] Originator/Creator
* [ ] Parent Case Owner (for child cases or subcases)

### What should the notification message say?

&nbsp;

&nbsp;

&nbsp;

&nbsp;


### How important is this message?
* [ ] Low
* [ ] Medium
* [ ] High


### Execute an external script or executable
If the action is to execute a script or executable, what is the external script or executable that should be executed?
&nbsp;

&nbsp;

&nbsp;

&nbsp;

### Send a message to Dovetail Carrier
If the action is to send a message to Dovetail Carrier, what is the message that should be sent?
&nbsp;

&nbsp;

&nbsp;

&nbsp;



### Repeating Action

Should this action repeat?
* [ ] No
* [ ] Yes

A repeating action should have a stop event. 
Example: Notify queue members when a case is dispatched to a queue. Keep notifying them every 4 hours until the case is accepted out of the queue.

### If this action should repeat, how often should it repeat? 

Example: Repeat every 4 hours, or every 30 days
How long should it keep repeating for?
Example: Repeat every 4 hours, *for the next 24 hours*

&nbsp;


---

## Action #2

### When should this action start?

Examples:
* Start this action immediately 
* Start this action if the case has been sitting in the queue for more than 4 hours
* Start this action 4 hours before the subcase is due

&nbsp;

&nbsp;

&nbsp;

&nbsp;

### Which calendar should be used?

* [ ] Elapsed Time
* [ ] Support Business Hours
* [ ] Customer Business Hours


### What action should happen when the rule fires?
* [ ] Notify people via a message (Email, In-app Notifications, SMS, etc.). This is the most common action.
* [ ] Execute an external script or executable
* [ ] Send a message to Dovetail Carrier

### Notification Message

If the action is to notify people:
Who should get notified?
This could be specific people, such as Fred, the Support Manager. Or it could be relative to the object that the rule fires for, such as the Case Owner, or the Current Queue Members. You can use a combination of both. 

#### Specific People:

&nbsp;



#### People relative to the object:

* [ ] Current Owner
* [ ] Current Owner’s Supervisor
* [ ] Contact
* [ ] Current Queue Members
* [ ] Originator
* [ ] Yanked From User
* [ ] Originator/Creator
* [ ] Parent Case Owner (for child cases or subcases)

### What should the notification message say?

&nbsp;

&nbsp;

&nbsp;

&nbsp;


### How important is this message?
* [ ] Low
* [ ] Medium
* [ ] High


### Execute an external script or executable
If the action is to execute a script or executable, what is the external script or executable that should be executed?
&nbsp;

&nbsp;

&nbsp;

&nbsp;

### Send a message to Dovetail Carrier
If the action is to send a message to Dovetail Carrier, what is the message that should be sent?
&nbsp;

&nbsp;

&nbsp;

&nbsp;



### Repeating Action

Should this action repeat?
* [ ] No
* [ ] Yes

A repeating action should have a stop event. 
Example: Notify queue members when a case is dispatched to a queue. Keep notifying them every 4 hours until the case is accepted out of the queue.

### If this action should repeat, how often should it repeat? 

Example: Repeat every 4 hours, or every 30 days
How long should it keep repeating for?
Example: Repeat every 4 hours, *for the next 24 hours*

&nbsp;



---

If your business rule needs more than 2 actions, simply include more actions that  follow the same pattern as above


