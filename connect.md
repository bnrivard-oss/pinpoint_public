---
title: Connect to QuickBooks — Claude Pnpt MCP
---

# Connect or reconnect to QuickBooks

[← Back](./)

Claude Pnpt MCP runs locally on the operator's own machine. Authorisation is started from
that machine rather than from this page, because the OAuth redirect returns to a local
listener.

## To connect a company

1. Open a terminal in the application directory.
2. Run:

   ```
   npm run login
   ```

3. A browser window opens Intuit's authorisation screen.
4. Choose the QuickBooks company to connect and approve access.
5. The terminal confirms the company name and realm ID once tokens are stored.

Repeat for each additional company. Each run adds a company rather than replacing one.

## To reconnect

Run the same command and choose the company that needs reconnecting. Intuit refresh tokens
expire after 100 days without use; reconnecting restores access.

## Confirming what is connected

```
npm run companies
```

This lists every connected company, which one is the default, and how long each
authorisation has left.

## Contact

Pinpoint Family Office Ltd.
benrivard@pinpt.ca
