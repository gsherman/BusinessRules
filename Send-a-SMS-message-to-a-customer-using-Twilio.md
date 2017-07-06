## Business Rule

|  |  |
| ------------- | ------------- |
| Description  |Send SMS message to a customer via Twilio |
| Object Type  | Case|
| Start Events| Log Note
| Condition 1 | Notes Log Type = SMS

## Rule Action #1

|  |  |
| ------------- | ------------- |
| Title	| Send SMS
| Action Type	| Carrier Message
| Start Action	| 0 minutes from Event Creation
| Repeat Every	| 0 minutes (Do Not Repeat)
| Create Activity Log When Action Fires?	| True

### Rule Action Message	
```
type=InvokeUrl
method=POST
contentType=application/x-www-form-urlencoded
url=https://api.twilio.com/2010-04-01/Accounts/1234567890/Messages.json
<HEADER>.Authorization=" Basic MyBase64EncodedCredentials"
To=[Contact Mobile Number]
From=[SupportTwilioSmsNumber]
Body="about case [Case ID] - [Notes Text]"
```

Requires:
* [Dovetail Rulemanager](https://support.dovetailsoftware.com/selfservice/products/show/RuleManager)
* [Dovetail Carrier](https://support.dovetailsoftware.com/selfservice/products/show/Dovetail%20Carrier)

## Rule Properties
* [Contact Mobile Number](Contact-Mobile-Number-Rule-Property)

## Notes
* This is an integration with [Twilio](https://twilio.com/), so you need a Twilio account.
* This is using the WebHooks Extension within Dovetail Carrier to make the web request to Twilio.

## Log a Note of Type SMS in Dovetail Agent

![](https://d26dzxoao6i3hh.cloudfront.net/items/013o0D193m1n0Y292h3n/LogNote.png)

## Example SMS Message
Here's an example of what the message looks like when received by the customer:

![](https://d26dzxoao6i3hh.cloudfront.net/items/0L1l0z313G36152i2x1t/sms.png)

