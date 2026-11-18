---
name: pagezero-sdk-installation
description: Install or verify the Page Zero SDK for Next.js, Laravel, or WordPress.
---

1. Use `getConnectionInfo` and `listSites` to identify the authorized website. Ask if the website is ambiguous. Pass its `site_id` to site tools.
2. Inspect the project to identify its framework. Use `getSdkInstallGuide` with the framework and the capabilities the user requested. Ask before adding a capability the user has not chosen.
3. Follow the commands and prerequisites in the guide. Run them in the intended project, and check that the selected site matches the authorized `site_id`. If the guide has no supported steps, report that instead of guessing a command, version, or download URL.
4. If sign-in is required, let the user complete it in the host. The MCP connection and the website SDK require separate authorization. Keep credentials out of chat and project files.
5. Run the checks in the guide. Use `getSdkStatus`, `listSdkObservations`, and the available doctor report tools to verify what the service received. Distinguish current results from past observations.

If the host cannot read local files or run commands, give the user the steps from the guide and explain how to verify them.
