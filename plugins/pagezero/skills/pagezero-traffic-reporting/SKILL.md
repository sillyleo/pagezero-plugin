---
name: pagezero-traffic-reporting
description: Read crawler, referral, and Google Analytics traffic, or save a report on request.
---

1. Use `getConnectionInfo` and `listSites` to identify the authorized website. Ask if the website is ambiguous. Pass its `site_id` to site tools. Confirm the reporting period and page scope.
2. For an existing report, use `listReports` and `getReport`. For current data, choose the available tools for the requested channel, such as `getCrawlerStats`, `getReferralStats`, or `listGa4PageTraffic`. Read all pages of results needed for the answer.
3. Keep crawler requests, observed referrals, and GA4 sessions separate. Report the period, sources, and limitations. Treat missing observations or a disconnected source differently from a measured zero.
4. Use `generateCrawlerReport` only if the user asks to save a new report. Check the returned report and its period before claiming it was saved. Check for an existing result before retrying.

If a data source or permission is missing, explain which part of the report it affects.
