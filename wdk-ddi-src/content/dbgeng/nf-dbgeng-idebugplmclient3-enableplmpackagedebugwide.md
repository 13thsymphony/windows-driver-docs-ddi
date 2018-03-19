---
UID: NF:dbgeng.IDebugPlmClient3.EnablePlmPackageDebugWide
title: IDebugPlmClient3::EnablePlmPackageDebugWide method
author: windows-driver-content
description: Enables a Process Lifecycle Management (PLM) package debug.
old-location: debugger\idebugplmclient3_enableplmpackagedebugwide.htm
old-project: debugger
ms.assetid: 6373B8BD-264D-4D03-9FE9-F87E45D617EE
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EnablePlmPackageDebugWide method [Windows Debugging], EnablePlmPackageDebugWide method [Windows Debugging], IDebugPlmClient3 interface, EnablePlmPackageDebugWide,IDebugPlmClient3.EnablePlmPackageDebugWide, IDebugPlmClient3, IDebugPlmClient3 interface [Windows Debugging], EnablePlmPackageDebugWide method, IDebugPlmClient3::EnablePlmPackageDebugWide, dbgeng/IDebugPlmClient3::EnablePlmPackageDebugWide, debugger.idebugplmclient3_enableplmpackagedebugwide
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
-	IDebugPlmClient3.EnablePlmPackageDebugWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# EnablePlmPackageDebugWide method
Enables a Process Lifecycle Management (PLM) package debug.

## Syntax

````
HRESULT EnablePlmPackageDebugWide(
  [in] ULONG64 Server,
  [in] PCWSTR  PackageFullName
);
````

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

<a href="..\dbgeng\nn-dbgeng-idebugplmclient3.md">IDebugPlmClient3</a>