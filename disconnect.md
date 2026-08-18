---
title: Disconnect from QuickBooks — Claude Pnpt MCP
---

# Disconnect from QuickBooks

[← Back](./)

You can revoke Claude Pnpt MCP's access to a QuickBooks company at any time. Doing so takes
effect immediately and does not alter any accounting data already recorded in QuickBooks.

## Revoke access in QuickBooks (recommended)

This is the authoritative step — it invalidates the application's tokens at Intuit.

1. Sign in to QuickBooks Online.
2. Go to **Settings (gear icon) → Apps**, or visit
   [https://qbo.intuit.com/app/appstore/appstore-mytab](https://qbo.intuit.com/app/appstore/appstore-mytab).
3. Find **Claude Pnpt MCP** in the connected apps list.
4. Choose **Disconnect** and confirm.

## Remove locally stored tokens

Because the application stores its tokens on the operator's own machine, remove them there
as well.

To disconnect one company:

```
npm run companies -- --remove "Company Name"
```

To remove every stored authorisation:

```
npm run logout
```

This deletes `tokens.json`. No accounting data is stored locally, so nothing else remains.

## What is retained after disconnecting

Nothing on any server — the application has none. Any invoice PDFs previously downloaded to
the operator's machine remain in the local `invoices` folder until deleted manually.

Records created in QuickBooks while the application was connected remain in QuickBooks, as
they are your own accounting data.

## Contact

Pinpoint Family Office Ltd.
benrivard@pinpt.ca
