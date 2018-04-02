---
UID: NF:dbgeng.IDebugPlmClient3.DisablePlmPackageDebugWide
title: IDebugPlmClient3::DisablePlmPackageDebugWide method
author: windows-driver-content
description: Disables a Process Lifecycle Management (PLM) package debug.
old-location: debugger\idebugplmclient3_disableplmpackagedebugwide.htm
old-project: debugger
ms.assetid: 23A5BAC2-E8F3-47FF-9B63-3FFF447C33B4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: DisablePlmPackageDebugWide method [Windows Debugging], DisablePlmPackageDebugWide method [Windows Debugging], IDebugPlmClient3 interface, DisablePlmPackageDebugWide,IDebugPlmClient3.DisablePlmPackageDebugWide, IDebugPlmClient3, IDebugPlmClient3 interface [Windows Debugging], DisablePlmPackageDebugWide method, IDebugPlmClient3::DisablePlmPackageDebugWide, dbgeng/IDebugPlmClient3::DisablePlmPackageDebugWide, debugger.idebugplmclient3_disableplmpackagedebugwide
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
-	IDebugPlmClient3.DisablePlmPackageDebugWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugPlmClient3::DisablePlmPackageDebugWide method
Disables a Process Lifecycle Management (PLM) package debug.

## Syntax

```
HRESULT DisablePlmPackageDebugWide(
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