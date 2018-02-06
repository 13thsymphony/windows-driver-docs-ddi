---
UID: NF:winspool.PrinterMessageBoxW
title: PrinterMessageBoxW function
author: windows-driver-content
description: "."
old-location: print\printermessageboxw.htm
old-project: print
ms.assetid: F5E7FB7C-A38F-4DBA-9C98-9554FA80CC07
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PrinterMessageBoxW, winspool/PrinterMessageBoxW, print.printermessageboxw, PrinterMessageBoxW function [Print Devices]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winspool.h
apiname:
-	PrinterMessageBoxW
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---


# PrinterMessageBoxW function


## Syntax

````
DWORD WINAPI PrinterMessageBoxW(
  _In_ HANDLE     hPrinter,
       DWORD      Error,
  _In_ HWND       hWnd,
  _In_ LPWSTR     pText,
  _In_ LPWSTR     pCaption,
       DWORD      dwType
);
````

## Parameters

`hPrinter`



`Error`



`hWnd`



`pText`



`pCaption`



`dwType`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winspool.h |
| **Library** | NtosKrnl.exe |