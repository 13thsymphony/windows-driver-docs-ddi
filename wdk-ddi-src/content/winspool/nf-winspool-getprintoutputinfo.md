---
UID: NF:winspool.GetPrintOutputInfo
title: GetPrintOutputInfo function
author: windows-driver-content
description: "."
old-location: print\getprintoutputinfo.htm
old-project: print
ms.assetid: 0EC09215-48B1-4B71-9B4C-99A25C35269F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetPrintOutputInfo, GetPrintOutputInfo function [Print Devices], print.getprintoutputinfo, winspool/GetPrintOutputInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Winspool.h
api_name:
-	GetPrintOutputInfo
product:
- Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---


# GetPrintOutputInfo function


## Syntax

```
HRESULT GetPrintOutputInfo(
  HWND   hWnd,
  PCWSTR pszPrinter,
  HANDLE *phFile,
  PWSTR  *ppszOutputFile
);
```

## Parameters

`hWnd`



`pszPrinter`



`phFile`



`ppszOutputFile`




## Return Value

If this function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winspool.h |