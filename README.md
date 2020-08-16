# Github-bot
name: Discord Message Notify

on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - name: Discord Message Notify
      uses: appleboy/discord-action@0.0.3
      with:
        webhook_id: ${{ secrets.WEBHOOK_ID }}
        webhook_token: ${{ secrets.WEBHOOK_TOKEN }}
        color: "#48f442"
        username: "GitHub Bot"
        args: The ${{ github.event_name }} event triggered.
