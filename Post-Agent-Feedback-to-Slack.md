When application feedback is submitted within Dovetail Agent, an Action Item is created and dispatched to a queue.
When this happens, this rule will post the feedback to a [Slack](https://slack.com/) channel. 

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |Feedback received - post to Slack |
| Object Type  | Action Item|
| Start Events| Dispatch
| Condition 1 | Task Type = Feedback
| Condition 2 | Queue = Feedback

## Rule Action #1
|  |  |
| ------------- | ------------- |
| Title	| Post to Slack
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=InvokeUrl
method=POST
url=https://hooks.slack.com/services/12345/67890/ABCDEFGHI
contentType=application/json
channel=#support
text="Feedback Notification"
username=support-bot
attachments[0].fallback="Feedback Received: [Title] : [ConfigItem.Dovetail Agent URL.String]/action-items/[Action Item ID]"
attachments[0].title=[Title]
attachments[0].title_link="[ConfigItem.Dovetail Agent URL.String]/action-items/[Action Item ID]"
attachments[0].color="warning"
attachments[0].pretext="Feedback Received: [Title] "
attachments[0].thumb_url="https://mycompany.com/logo.jpg"
attachments[0].fields[0].title=Notes
attachments[0].fields[0].value="[Notes]"
attachments[0].fields[0].short=false
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager)
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Notes
* This is an integration with [Slack](https://slack.com/), so you need a Slack account.
* This is using the WebHooks Extension within Dovetail Carrier to make the web request to Slack.

## Example Slack Message
Here's an example of what the message looks like when posted to Slack:

![](https://d26dzxoao6i3hh.cloudfront.net/items/1Q2i1Z033y1T432Q463B/slack.png)

