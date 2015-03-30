# slackus
Disqus Slack integration

See https://github.com/jonathanwiesel/slackus

## Build

```bash
docker build -t hypriot/slackus .
```

## Run

```bash
docker run -e SLACKUS_DISQUS_API_KEY="xx" -e SLACKUS_DISQUS_API_SECRET="yy" -e SLACKUS_DISQUS_ACCESS_TOKEN="aa" -e SLACKUS_DISQUS_FORUM="hypriot" -e SLACKUS_SLACK_WEBHOOK="https://hooks.slack.com/services/xxyyzz" docker run -t hypriot/slackus
```
