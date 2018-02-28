---
UID: NF:winspool.PrinterMessageBoxA
title: PrinterMessageBoxA function
author: windows-driver-content
description: "."
old-location: print\printermessageboxa.htm
old-project: print
ms.assetid: 6C238FF8-1EBC-4E3B-9184-D82F5A39DA2F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PrinterMessageBoxA, PrinterMessageBoxA function [Print Devices], print.printermessageboxa, winspool/PrinterMessageBoxA
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Winspool.h
api_name:
-	PrinterMessageBoxA
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---


# PrinterMessageBoxA function


## Syntax

````
DWORD WINAPI PrinterMessageBoxA(
  _In_ HANDLE         hPrinter,
       DWORD          Error,
  _In_ HWND           hWnd,
  _In_ LPSTR          pText,
  _In_ LPSTR          pCaption,
       DWORD          dwType
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