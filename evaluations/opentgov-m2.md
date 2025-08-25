# General Notes

App successfully boots:
```ts
npm start

> OpenGov Voting Tool@1.3.0 start
> node dist/app.js

[2025-08-25 20:17:41] INFO: Starting OpenGov Voting Tool v1.3.0
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "app"
    deepSyncLimit: 100
    deepSyncHour: 3
    refreshInterval: "900"
[2025-08-25 20:17:41] INFO: Waiting until the start minute...
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "app"
[2025-08-25 20:17:41] INFO: Waiting until start minute...
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
[2025-08-25 20:17:41] INFO: Waiting until START_MINUTE
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    waitTimeSeconds: 2580
    startMinute: 0
[2025-08-25 20:17:41] INFO: No ready proposals found.
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "mimir"
```
