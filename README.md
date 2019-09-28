# watchdox

Reverse engineering digital rights management (DRM) used by Blackberry Workspaces to export secure documents.

## What is BlackBerry Workspaces?

*From [blackberry.com](https://www.blackberry.com/us/en/support/enterprise-apps/blackberry-workspaces)*

> BlackBerry® Workspaces[, formerly WatchDox,] is the leading secure EFSS solution, enabling users to share, edit and control their files on every device. Only BlackBerry Workspaces can provide the level of security organizations need — wherever files are, wherever they need to go, and whoever needs to access them. Workspaces embeds digital rights management (DRM) protection in your files, so your content remains secure everywhere it goes. With Workspaces, you stay in control – even after files are shared outside your firewall.

## What is this repository for?

This repository contains the updated production code that made it possible to bypass the DRM of the service and export secure documents based on BlackBerry Workspaces. The exploit takes advantage of the document data being stored within a JavaScript variable in memory and saves the file as a blob to the browser's downloads before the data is passed to [`PSPDFKit.load()`](https://pspdfkit.com/api/web/PSPDFKit.html#.load). Applying this updated script will require intercepting the JavaScript that the browser is using. This is easily achievable with [Chrome Local Overrides](https://developers.google.com/web/updates/2018/01/devtools#overrides).
