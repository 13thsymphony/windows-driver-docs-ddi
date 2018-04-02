---
UID: NF:dbgeng.IDebugPlmClient3.ResumePlmPackageWide
title: IDebugPlmClient3::ResumePlmPackageWide method
author: windows-driver-content
description: Resumes a Process Lifecycle Management (PLM) package.
old-location: debugger\idebugplmclient3_resumeplmpackagewide.htm
old-project: debugger
ms.assetid: CC69357E-425B-440B-93D0-918E8586D5DF
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugPlmClient3, IDebugPlmClient3 interface [Windows Debugging], ResumePlmPackageWide method, IDebugPlmClient3::ResumePlmPackageWide, ResumePlmPackageWide method [Windows Debugging], ResumePlmPackageWide method [Windows Debugging], IDebugPlmClient3 interface, ResumePlmPackageWide,IDebugPlmClient3.ResumePlmPackageWide, dbgeng/IDebugPlmClient3::ResumePlmPackageWide, debugger.idebugplmclient3_resumeplmpackagewide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugPlmClient3.ResumePlmPackageWide
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugPlmClient3::ResumePlmPackageWide method
Resumes a Process Lifecycle Management (PLM) package.

## Syntax

```
HRESULT ResumePlmPackageWide(
  ULONG64 Server,
  PCWSTR  PackageFullName
);
```

## Parameters

`Server`

The server of the package.

`PackageFullName`

A pointer to the package name.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/5B0580FF-0829-406A-B511-C0CD91A08D5F">IDebugPlmClient3</a>