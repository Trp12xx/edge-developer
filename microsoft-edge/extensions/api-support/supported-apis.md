---
ms.assetid: dc79bb0d-4fd8-4988-86d6-af60bec62b10
description: Find information on current and future APIs as well their known issues/Chrome incompatibilities.
title: Extensions - Supported APIs
author: abbycar
ms.author: abigailc
ms.date: 02/08/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
---

#  Supported APIs

The following is a detailed list of API members that are supported. Development of the extension platform is ongoing, so check back frequently for updates!

> [!NOTE]
> For Microsoft Edge, all extension APIs are under the `browser` namespace, e.g. `browser.browserAction.disable()`.


## Overarching issues

The following known issues span across the extension platform and will be fixed in the near future:

- Regardless of any `catch()` statements, exceptions thown in the content script context by predefined JavaScript methods (such as `document.querySelector()`) will be dispatched to both the content script's and page's `window.onerror` handlers.
- When using the CSS `url()` property, absolute URLs using `ms-browser-extension://` will not work like they do in Chrome. To bypass this issue, use relative paths to resources (starting in the root extension directory) instead.
- `window.open()` does not work in extension background scripts. Please use `browser.windows.create()` instead.

## browserAction

The following `browserAction` APIs are supported:

| API                                   | Known issues                                             | Chrome incompatibilities
|---------------------------------------|----------------------------------------------------------|--------------------------|
| [browserAction](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/browserAction) | | |
| [browserAction.disable](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/disable) | | |
| [browserAction.enable](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/enable) | | |
| [browserAction.getBadgeBackgroundColor](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeBackgroundColor) |  | |
| [browserAction.setBadgeBackgroundColor](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeBackgroundColor) | | Only `ColorArray` and hexidecimal values are supported. CSS color names (i.e. `blue`) are not. |
| [browserAction.onClicked](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/onClicked) | | |
| [browserAction.setBadgeText](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeText)            | | |
| [browserAction.setPopup](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/browserAction/setPopup)  | | |
| [browserAction.getBadgeText](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeText)   | | |
| [browserAction.setIcon](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setIcon) | `browserAction.setIcon` is not persisted. <br/><br/> The `imageData` parameter is not supported. <br/><br/> `path` is a required parameter.| |

## contextMenus

The following `contextMenus` APIs are supported:

| API                    | Known issues | Chrome incompatibilities
|------------------------|--------------|----------------------|
| [contextMenus](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus)  |  | |
| [contextMenus.ContextType](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/contextMenus/ContextType) | `"page_action"` `ContextType` will not show up in the page action context menu.| Microsoft Edge does not support the `"launcher"` `ContextType`.|
| [contextMenus.create](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/create)    | When extensions do not provide a `contextmenuid`, the `id` generated is not unique. | |
| [contextMenus.onClicked](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/onClicked) | | |
| [contextMenus.remove](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/remove) | | |
| [contextMenus.removeAll](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/removeAll) | | |
| [contextMenus.update](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/update) | | |

## cookies

The following `cookies` APIs are supported:

| API                    | Known issues | Chrome incompatibilities
|------------------------|--------------|----------------------|
| [cookies](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/cookies)  |  | |
| [cookies.get](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/cookies/get)    |  | |
| [cookies.getAll](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/cookies/getAll) |   | If no URL is provided, cookies are retrieved only for URLs in currently opened tabs. In Chrome, this gets all cookies on a user’s machine. |
| [cookies.getAllCookieStores](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/cookies/getAllCookieStores)  | | Always returns the same default cookie store with ID “0”. All cookies belong to this store. |
| [cookies.onChanged](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/cookies/onChanged)    | | Not supported. |
| [cookies.remove](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/cookies/remove) |  | |
| [cookies.set](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/cookies/set)    |  | |



## extension

The following `extension` APIs are supported:

| API                                   | Known issues | Chrome incompatibilities
|---------------------------------------|----------------------------------------------------------|-------------|
[extension](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/extension) | | |
[extension.getBackgroundPage](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/extension/getBackgroundPage) | | |
[extension.getURL](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/extension/getURL) | | |
[extension.getViews](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/extension/getViews) | | |


## i18n

The following `i18n` APIs are supported:

API | Known issues | Chrome incompatibilities
:------| :-------- | :---------------------
[i18n](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/i18n) | | |
[i18n.getAcceptLanguages](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getAcceptLanguages) | | |
[i18n.getMessage](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/i18n/getMessage) | `i18n.getMessage` with invalid key throws exception instead of failing gracefully. <br/><br/> `i18n.getMessage` argument expects strings, but should also allow an int or throw an exception. | |
[i18n.getUILanguage](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getUILanguage) | | |

## idle

The following `idle` APIs are supported:

API | Known issues | Chrome incompatibilities
:------| :-------- | :---------------------
[idle](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/idle) | | |
[idle.setDetectionInterval](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/idle/setDetectionInterval) | | |
[idle.queryState](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/idle/queryState) | | |
[idle.onStateChanged](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/idle/onStateChanged) | | |


## pageAction

The following `pageAction` APIs are supported:

API | Known issues | Chrome incompatibilities
:------------ | :------------- | :--------------------
[pageAction](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/pageAction) | | |
[pageAction.getPopup](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getPopup) | | |
[pageAction.getTitle](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getTitle) | | |
[pageAction.hide](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/hide) | | |
[pageAction.onClicked](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/onClicked) | | |
[pageAction.setIcon](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setIcon) | | The `imageData` parameter is not supported. <br/><br/> `path` is a required parameter. |
[pageAction.setPopup](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setPopup) | | |
[pageAction.setTitle](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setTitle) | | |
[pageAction.show](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/show) | | |



## runtime

The following `runtime` APIs are supported:

API | Known issues | Chrome incompatibilities
:------------ | :------------- | :-------------------
[runtime](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/runtime) | | |
[runtime.connect](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/runtime/connect) | | |
[runtime.id](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/runtime/id) | | |
[runtime.getBackgroundPage](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/runtime/getBackgroundPage) | | |
[runtime.getManifest](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getManifest) | | |
[runtime.getURL](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getURL) | | |
[runtime.lastError](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/runtime/lastError) | | |
[runtime.onConnect](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/runtime/onConnect) | | |
[runtime.onInstalled](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onInstalled) | | |
[runtime.onMessage](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onMessage) | `tab` object in `runtime.onMessage` event is not fully implemented. | `MessageSender.tlsChannelId` is not supported in Microsoft Edge.|
[runtime.sendMessage](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/runtime/sendMessage) | Microsoft Edge extension pages can use `runtime.sendMessage`/`onMessage` to send messages to themselves. <br/><br/> `runtime.sendmessage` is not supported from site pages. | Microsoft Edge does not support the `options` parameter.|

## storage

The following `storage` APIs are supported:

API | Known issues | Chrome incompatibilities
:------------ | :------------- | :------------------------
[storage](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/storage) |  | |
[storage.local.get](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/Storage/StorageArea/get)  | | |
[storage.local.set](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/Storage/StorageArea/set)  | | |
[storage.local.remove](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/Storage/StorageArea/remove)  | | |
[storage.local.clear](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/Storage/StorageArea/clear) | | |
[storage.local.getBytesInUse](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/Storage/StorageArea/getBytesInUse) | | `storage.local` data is persisted in a different format than Chrome, causing a different value to be returned when calling `storage.local.getBytesInUse`.  <br/><br/>Ex: `storage.local.set({ "k": { "s": "âas" } }` returns 13 in Chrome and 50 in Microsoft Edge.|
[storage.onChanged](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/storage/onChanged) | | |

## tabs

The following `tabs` APIs are supported:

API | Known issues | Chrome incompatibilities
:------------ | :------------- | :----------------
[tabs](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs) | | |
[tabs.create](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/create) | | `selected`, `pinned`, and `openerTabId` are not supported. |
[tabs.detectLanguage](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/detectLanguage) | | |
[tabs.executeScript](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/executeScript) | `runAt` is ignored, though checked.| |
[tabs.get](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/get) | Options pages, when asking about a tab not in their window, fail this call. | |
[tabs.getCurrent](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/getCurrent) | | |
[tabs.insertCSS](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/insertCSS) | `runAt` is ignored, though checked. | |
[tabs.update](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/tabs/update) | | |
[tabs.onActivated](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onActivated) | | |
[tabs.onCreated](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onCreated) | | |
[tabs.onRemoved](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onRemoved) | | |
[tabs.onReplaced](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/tabs/onReplaced) | | |
[tabs.onUpdated](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onUpdated) | After uninstall/reinstall, the URL is not received until Microsoft Edge is restarted. | |
[tabs.query](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/query) | `pinned`, `audible`, and `muted` are not yet supported. <br/><br/> `"popup"` `windowType` is not yet supported. | `highlighted` is not supported. <br/><br/> `"panel"`, `"app"`, and `"devtools"` `windowType` are not supported. |
[tabs.remove](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/remove) | | |
[tabs.sendMessage](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/sendMessage) | Messaging a specific frame is not yet supported. `tabs.sendMessage` never sends a response after a tab refresh if no `runtime.onMessage` listeners are present on the receiving tab. | |
[tabs.Tab](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/Tab) | `audible`, `mutedInfo`, `inPrivate`, `width`, and `height` properties are not yet supported. | `openerTabId`, `selected`, and `highlighted` properties are not supported. |
[tabs.update](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/tabs/update) | `pinned` and `muted` are not yet supported. | `highlighted` and `selected` are not supported. |


## webNavigation

The following `webNavigation` APIs are supported:

API | Known issues | Chrome incompatibilities
:------ | :----- | :-------
[webNavigation](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation) | Tab ids are incorrect. | Filtering, TransitionTypes and TransitionQualifiers not supported. <br/><br/> For a tab, all `processIds` will be the same. |
[webNavigation.getAllFrames](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getAllFrames) | Does not include object-as-iframe elements. | |
[webNavigation.getFrame](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getFrame) | | |
[webNavigation.onBeforeNavigate](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onBeforeNavigate) | | |
[webNavigation.onCommited](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webNavigation/onCommitted) | | |
[webNavigation.onCompleted](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCompleted) | | |
[webNavigation.onCreatedNavigationTarget](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCreatedNavigationTarget) | | |
[webNavigation.onDOMContentLoaded](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onDOMContentLoaded) | | |
[webNavigation.onErrorOccurred](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onErrorOccurred) | | |
[webNavigation.onHistoryStateUpdated](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onHistoryStateUpdated) | | |
[webNavigation.onReferenceFragmentUpdated](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webNavigation/onReferenceFragmentUpdated) | | |
[webNavigation.onTabReplaced](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onTabReplaced) | | Not supported. | |
[webNavigation.TransitionType](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionType) | | |
[webNavigation.TransitionQualifier](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionQualifier) | | |

## webRequest

The following `webRequest` APIs are supported:

API | Known issues | Chrome incompatibilities
:------ | :----- | :-------
[webRequest](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest) | `webRequest` not supported for synchronous `XmlHttpRequests`. | Network requests from extensions, such as options, background or popup pages, are not supported.<br/><br/> Network requests from `<object>` and `<embed>` elements are not supported.<br/><br/> Headers cannot be modified for cached requests.  |
[handlerBehaviorChanged](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/handlerBehaviorChanged) | | Handler changes are automatically handled in Microsoft Edge.<br/><br/>Calling this has no effect.  |
[onAuthRequired](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/onAuthRequired) | | |
[onBeforeRedirect](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/onBeforeRedirect) | | |
[onBeforeRequest](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/onBeforeRequest) | | `requestBody` is not supported. |
[onBeforeSendHeaders](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/onBeforeSendHeaders) | | |
[onCompleted](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/onCompleted) | | |
[onErrorOccurred](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/onErrorOccurred) | | |
[onHeadersReceived](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/onHeadersReceived) | |  |
[onResponseStarted](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/onResponseStarted) | |  |
[onSendHeaders](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/webRequest/onSendHeaders) | | |

## windows

The following `windows` APIs are supported:

API | Known issues | Chrome incompatibilities
:------------ | :------------- | :-------------------
[windows](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/windows) | | `Window` objects do not support `alwaysOnTop` property in Microsoft Edge. <br/><br/>InPrivate is not supported.|
[windows.CreateType](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/windows/CreateType) | | `"panel"` and `"detached_panel"` are not supported in Microsoft Edge. |
[windows.create](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/windows/create) | | `tabId` parameter for tearing off a tab is not supported. |
[windows.get](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/windows/get) | | |
[windows.getAll](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/windows/getAll) | `windows.getAll({populate: true})` is missing `tabs` property. | | |
[windows.getCurrent](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/windows/getCurrent) | | |
[windows.getLastFocused](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/windows/getLastFocused) | | |
[windows.update](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/windows/update) | Specifying position is not supported. | `"minimized"`/`"maximized"`/`"fullscreen"` and `drawAttention` are not supported in Microsoft Edge. |
[windows.onCreated](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/windows/onCreated) | | `WindowType` filter is not supported. |
[windows.onFocusChanged](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/windows/onFocusChanged) | | `WindowType` filter is not supported. |
[windows.WindowState](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/windows/WindowState) | `"minimized"`,`"maximized"`, `"fullscreen"` are not supported.| `"docked"` is not supported in Microsoft Edge. |
[windows.WindowType](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/windows/WindowType) | | `"panel"`, `"app"`, and `"devtools"` are not supported in Microsoft Edge. |
[windows.WINDOW_ID_CURRENT](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_CURRENT) | | |
[windows.WINDOW_ID_NONE](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_NONE) | | |
