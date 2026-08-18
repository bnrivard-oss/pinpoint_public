# Privacy Policy

**Application:** Claude Pnpt MCP
**Provider:** Pinpoint Family Office Ltd. ("we", "us")
**Effective date:** 17 August 2026

---

## 1. Scope

This policy describes how the Claude Pnpt MCP application ("the Application") handles data.
The Application is a private, internal-use integration between QuickBooks Online and the
Model Context Protocol. It is not offered to the public and does not have external users
beyond authorised personnel of Pinpoint Family Office Ltd.

## 2. What the Application accesses

With your authorisation through Intuit's OAuth 2.0 consent flow, the Application accesses
data in the QuickBooks Online companies you explicitly connect, under the
`com.intuit.quickbooks.accounting` scope. This can include:

- company profile information (name, address, fiscal year, tax settings);
- financial reports (profit and loss, balance sheet, cash flow, aged receivables and payables);
- transactions (invoices, bills, payments, purchases, journal entries);
- lists (customers, vendors, items, chart of accounts, tax codes).

The Application can also **create and modify** records in connected companies, and can send
invoice emails to addresses recorded in QuickBooks.

The Application does **not** access QuickBooks Payroll, and does not request payment-card
data or bank credentials.

## 3. Where data is stored

**The Application has no server and no hosted database.** It runs entirely on the local
machine of the person using it.

- **OAuth tokens** (access token, refresh token, and the QuickBooks company/realm ID) are
  stored in a local file, `tokens.json`, in the application directory, with
  owner-only file permissions. They are never transmitted anywhere except to Intuit.
- **API credentials** (client ID and secret) are stored in a local `.env` file and are never
  transmitted anywhere except to Intuit.
- **Accounting data** is fetched from Intuit on demand and held in memory to answer the
  request. The Application maintains no cache or copy of your financial records.
- **Downloaded documents** (such as invoice PDFs) are written to a local folder only when
  explicitly requested, and remain on your machine.

## 4. Who data is shared with

We do not sell, rent, or trade any data. Data reaches only the following parties:

**Intuit Inc.** — All accounting data comes from, and all write operations go to, Intuit's
QuickBooks Online API. Intuit's handling of that data is governed by Intuit's own privacy
policy.

**Anthropic PBC** — The Application's purpose is to make QuickBooks data available to Claude.
Accordingly, **data retrieved from QuickBooks is transmitted to Anthropic** to be processed
in the course of answering the request. This is inherent to how the Application works.
Anthropic's handling of that data is governed by Anthropic's privacy policy and by the terms
of the Anthropic plan in use.

**Email recipients** — When an invoice is emailed, Intuit delivers it to the address recorded
on the invoice.

No other third party receives data from the Application. There are no analytics,
telemetry, advertising, or tracking components.

## 5. Retention

Because there is no server, we retain nothing centrally. Locally stored data persists until
deleted:

- OAuth tokens persist until you disconnect a company or delete `tokens.json`. Intuit refresh
  tokens expire after 100 days without use.
- Downloaded documents persist until you delete them.

To remove all stored authorisation, delete `tokens.json` and revoke the Application in
QuickBooks Online under **Settings → Apps**.

## 6. Security

- Credentials and tokens are stored locally with restricted file permissions and are excluded
  from version control.
- All communication with Intuit uses HTTPS.
- Access tokens are short-lived and refreshed automatically; refresh tokens are rotated by
  Intuit.
- Security of the underlying device — disk encryption, account access, and physical control —
  is the responsibility of the person operating it.

## 7. Your rights

The data handled by the Application is your own QuickBooks data, held in your Intuit account.
You may access, correct, export, or delete it directly in QuickBooks Online at any time, and
may revoke the Application's access at any time as described above.

Where Canadian privacy legislation (including PIPEDA) applies to personal information in your
accounting records, you retain all rights afforded under that legislation.

## 8. Children

The Application is a business accounting tool and is not directed at or intended for use by
anyone under 18.

## 9. Changes

We may update this policy. The effective date above indicates the current version.

## 10. Contact

Questions about this policy, or about data handled by the Application:

**Pinpoint Family Office Ltd.**
benrivard@pinpt.ca
