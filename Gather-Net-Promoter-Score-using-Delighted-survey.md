When a case is closed, call the [Delighted](https://delighted.com/) API to send the customer a one question survey, in order to track Net Promoter Score.

## Business Rule

|  |  |
| ------------- | ------------- |
| Description  | Gather Net Promoter Score using a Delighted survey |
| Object Type  | Case  |
| Start Events| Close Task

## Rule Action #1
|  |  |
| ------------- | ------------- |
| Title	| Call Delighted API
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=InvokeUrl
method=POST
url=https://@api.delightedapp.com/v1/people.json
contentType=application/json
<HEADER>.Authorization=Basic Your64bitEncodedApiKey
email=[Contact Email]
```
Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager)
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Notes
* This is an integration with [Delighted](https://delighted.com/), so you need a Delighted account.
* This is using the WebHooks Extension within Dovetail Carrier to make the web request to Delighted.

## Example Survey Email
Here's an example of what the email looks like that is sent to the customer:

![](https://d26dzxoao6i3hh.cloudfront.net/items/2U0O1O452d422B2s0A2j/delighted.png)

