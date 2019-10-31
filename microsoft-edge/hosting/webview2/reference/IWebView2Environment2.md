---
description: Host web content in your Win32 app with the Microsoft Edge WebView2 control
title: Microsoft Edge WebView2 for Win32 apps
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/25/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, webview2, webview, win32 apps, win32, edge
---

# interface IWebView2Environment2 

```
interface IWebView2Environment2
  : public IWebView2Environment
```

Additional functionality implemented by the Environment object.

## Summary

 Members                        | Descriptions
--------------------------------|---------------------------------------------
[get_BrowserVersionInfo](#get_browserversioninfo) | The browser version info of the current [IWebView2Environment](IWebView2Environment.md#interface_i_web_view2_environment), including channel name if it is not the stable channel.

See the [IWebView2Environment](IWebView2Environment.md#interface_i_web_view2_environment) interface for more details. You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md#interface_i_web_view2_environment).

## Members

#### get_BrowserVersionInfo 

The browser version info of the current [IWebView2Environment](IWebView2Environment.md#interface_i_web_view2_environment), including channel name if it is not the stable channel.

> public HRESULT [get_BrowserVersionInfo](#interface_i_web_view2_environment2_1ac35fa177e54a9fb827e589e0095b2bfa)(LPWSTR * versionInfo)

This matches the format of the GetWebView2BrowserVersionInfo API. Channel names are 'beta', 'dev', and 'canary'.

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(nullptr, version_info.get(), L"Browser Version Info After WebView Creation", MB_OK);
```
