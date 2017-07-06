When a case is dispatched, this rule will post the case to a [Slack](https://slack.com/) channel. 

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |Case Dispatched - post to Slack |
| Object Type  | Case|
| Start Events| Dispatch
| Condition 1 | Case Type = Support

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
url=https://hooks.slack.com/services/api/mysecrettoken
method=POST
contentType=application/json
channel=#support
text=Case Dispatch Notification
username=support-bot
attachments[0].fallback=[DovetailAgentURL]/support/cases/[Object ID]
attachments[0].title="[Title]"
attachments[0].title_link=[DovetailAgentURL]/support/cases/[Object ID]
attachments[0].color="warning"
attachments[0].pretext=[DovetailAgentURL]/support/cases/[Object ID]
attachments[0].thumb_url="https://myserver.com/images/logo.jpg"
attachments[0].fields[0].title=Severity
attachments[0].fields[0].value=[Severity]
attachments[0].fields[0].short=false
attachments[0].fields[1].title=Queue
attachments[0].fields[1].value=[Current Queue]
attachments[0].fields[1].short=false
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager)
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Notes
* This is an integration with [Slack](https://slack.com/), so you need a Slack account.
* This is using the WebHooks Extension within Dovetail Carrier to make the web request to Slack.

## Example Slack Message
Here's an example of what the message looks like when posted to Slack:

![](https://d26dzxoao6i3hh.cloudfront.net/items/2f290H13262v3R2a3k2I/slack-dispatch.png)

