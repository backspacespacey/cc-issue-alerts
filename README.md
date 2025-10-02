# cc-issue-alerts
Slack webhook automatic notifications for codecademy docs new issues

# Issue Alerts to Slack

This repository runs a GitHub Actions workflow that checks for **new issues** created in [`Codecademy/docs`](https://github.com/Codecademy/docs).  
When a new issue is detected, the workflow posts a notification into a designated **Slack channel** using an Incoming Webhook.

## How it works
- The workflow runs automatically every 5 minutes (via `cron`).
- It queries the GitHub Issues API for the `Codecademy/docs` repository.
- Any new issues created in the last ~6 minutes are posted to Slack.
- The Slack Incoming Webhook URL is stored securely as a GitHub Secret (`SLACK_WEBHOOK_URL`).

## Setup (already done)
1. Create a Slack Incoming Webhook and choose a target channel.
2. Add the webhook URL as a repository secret named `SLACK_WEBHOOK_URL`.
3. Place the workflow file under `.github/workflows/notify-new-issues.yml`.

## Notes
- This is a **private utility repo** used only for automation. (changed to public)
- Secrets are never exposed in the workflow logs.
- You can adjust the cron schedule (`*/5 * * * *`) in the YAML file if you want faster or slower checks.
- currently running on this slack channel https://join.slack.com/t/stacked-up/shared_invite/zt-3e4cq37f8-wR1wph0wESz8W6SGunTBvQ -- join, enjoy, and have fun, Happy Coding!
