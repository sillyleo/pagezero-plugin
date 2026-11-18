---
name: pagezero-visibility-tracking
description: Review keyword and AI visibility history, or start and stop tracking on request.
---

1. Use `getConnectionInfo` and `listSites` to identify the authorized website. Ask if the website is ambiguous. Pass its `site_id` to site tools.
2. Use `listTrackedKeywords`, `listTrackedPrompts`, or `getTrackingSchedule` to find the requested tracking target. Use its returned ID for results. Keep the platform, date range, and sample units consistent when comparing results.
3. Start tracking with `trackKeyword` or `trackPrompt` only when the user asks. For prompt tracking, use platforms supported by the current tool schema. If the user has no preference, ask which platform to track. Starting tracking may use plan allowance. Check the last result before retrying.
4. Use `untrackKeyword` or `untrackPrompt` only when asked to stop future tracking. Existing reports and any work already in progress may remain available.
5. If a tool returns a `workflow_run_id`, use `getWorkflowResult` to check progress. A scheduled run is not a new observation. Report missing samples separately from a measured result.

If a platform, tool, or permission is unavailable, explain what you could verify.
