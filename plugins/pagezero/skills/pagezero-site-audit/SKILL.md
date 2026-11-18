---
name: pagezero-site-audit
description: Read existing audit findings or run a requested audit for an authorized website.
---

1. Use `getConnectionInfo` and `listSites` to identify the authorized website. Ask if the website is ambiguous. Pass its `site_id` to site tools.
2. Start with existing findings. Use `listSitePages`, `getPageAudit`, or `listAuditRuns` and `getAuditRun` as needed. Report which pages and dates the findings cover.
3. Start a new audit only when the user asks. Choose `auditUrl` for a page, `auditSiteWide` for a website, or `searchFoundationAudit` for a search readiness check. Follow the current tool schema. A new audit may use plan allowance, so check for an existing result before retrying.
4. If a tool returns a `workflow_run_id`, use `getWorkflowResult` to check progress and read the result. Report queued, failed, and completed work accurately. If the audit could not read part of a page, describe the limitation instead of treating it as a defect.

If a tool is unavailable or needs additional access, explain the limitation and ask the user to reconnect if required.
