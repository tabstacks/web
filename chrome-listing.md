# TabStacks: Auto-group tabs by domain

## Summary

Automatically group tabs by site and switch between them without the clutter.

## Description

TabStacks keeps your browser organized automatically. Open two or more tabs from the same site and they snap into a named Chrome tab group, no dragging required. A dismissible slim switcher bar lets you jump between tabs in the group without ever leaving the page you're on.

## Features

- **Auto Stacking** — tabs from the same site group automatically, no dragging or manual sorting
- **Fast Switching** — keyboard shortcuts jump to the next or previous tab in a stack
- **Stack Dashboard** — view every active stack, tab count, and current tab from the popup
- **Custom Thresholds** — choose whether stacking starts at 2, 3, 4, or 5 tabs
- **Quick Close** — close individual tabs from the popup without switching to them
- **Light & Dark Themes** — switch themes manually from the popup
- **Private by Design** — tab data stays in your browser and is never sold or shared

## Privacy & Permissions

### Single purpose

TabStacks organizes browser tabs by website domain into lightweight, collapsible groups and provides a simple in-page switcher to quickly switch between tabs from the same site.

### Host permissions

The extension injects a lightweight tab-switcher UI into stacked tabs, including background tabs. Broad host permissions are required so the switcher can be injected into and updated on tabs that are not currently active.

The injected script only renders the switcher bar. It does not read, extract, or transmit any page content.

`activeTab` is insufficient because tabs must be reachable when they are not the active tab. Without broad host permissions, the switcher bar cannot be injected into or updated on background tabs, causing non-active tabs in a stack to show stale or missing switcher UI.

### Tabs permission

This extension needs the `tabs` permission to detect and manage open tabs so it can automatically group tabs by website domain and provide a compact switcher for quickly switching between same-site tabs. Only tab metadata such as hostname, title, and tab id is read and stored locally for grouping. No page content or browsing history is transmitted off the device, and users can disable the feature at any time.

### TabGroups permission

This extension needs the `tabGroups` permission to create and manage Chrome Tab Groups used for lightweight, site-specific stacks. The API is used only to create groups, set their collapsed state, and move tabs into or out of those groups so users can quickly switch between and collapse same-site tabs. Only group metadata is stored locally; no page content or browsing data is sent off the device. Users can turn off the feature at any time.

### Storage permission

This extension uses the `storage` permission to persist extension settings and extension-owned stack metadata such as site hostname, extension-owned group id, primary tab id, and collapsed state so tab stacks remain consistent across browser and service worker restarts. Only minimal metadata is stored locally and is not transmitted off-device. Users can disable the feature to clear stored state.

### Scripting permission

This extension uses the `scripting` permission to inject a small content script and CSS that render a compact in-page switcher for same-site tabs and handle switch actions. The injected code only displays the UI and receives sanitized stack metadata from the extension. It does not read page content or transmit data externally. Users can disable the feature to stop in-page injections.

### Host permissions

Host permissions are limited to `http://*/*` and `https://*/*` to allow insertion of a small in-page switcher on sites the user enables. The injected script only renders UI and consumes sanitized tab metadata such as title and origin. It does not access or transmit page content. Non-web schemes, including browser internals, local files, and extension pages, are excluded.
