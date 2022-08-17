# slack curl post to webhook
```bash
curl -X POST --data-urlencode "payload={\"channel\": \"#channel-name\", \"username\": \"webhookbot\", \"text\": \"This is posted to #channel-name and comes from a bot named webhookbot.\", \"icon_emoji\": \":ghost:\"}" https://hooks.slack.com/services/{your-webhook-id}
```
