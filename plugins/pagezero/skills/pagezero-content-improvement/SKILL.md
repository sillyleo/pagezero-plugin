---
name: pagezero-content-improvement
description: Review and improve Page Zero AEO content, check publication and delivery, or export a website on request.
---

1. Use `getConnectionInfo` and `listSites` to identify the authorized website. Ask if the website is ambiguous. Pass its `site_id` to site tools.
2. Read the current content with `listAeoContents` and `getAeoContent`. Follow the returned pagination fields and keep all parts of a document on the same revision.
3. If the user asks for changes, choose an available tool such as `editAeoArtifact` or `generateAeoContent`. Generation and editing commands can publish content and use plan allowance. For a draft or review, use a draft tool if available, or give suggestions in chat. Keep the live site unchanged. Check the result before retrying a command that can change data or incur a charge.
4. When the user explicitly asks to publish or withdraw content, use `setAeoPublication`. Check the saved content with `getAeoContent` and delivery with `getAeoDeliveryStatus`. Report whether the destination has confirmed delivery.
5. Start `prepareHandoffExport` only when the user asks for an export. Check `getExportStatus`, then use the manifest and file tools to retrieve and verify the result. Keep site export data private.

Follow the current tool schemas and the user's permissions. If a tool is unavailable or needs additional access, explain the limitation.
