---
UID: NF:dbgeng.IDebugPlmClient3.QueryPlmPackageList
title: IDebugPlmClient3::QueryPlmPackageList method
author: windows-driver-content
description: Query a Process Lifecycle Management (PLM) package list.
old-location: debugger\idebugplmclient3_queryplmpackagelist.htm
old-project: debugger
ms.assetid: BAAAF09B-F39D-44E0-9409-1C98B0C6A56B
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugPlmClient3, IDebugPlmClient3 interface [Windows Debugging], QueryPlmPackageList method, IDebugPlmClient3::QueryPlmPackageList, QueryPlmPackageList method [Windows Debugging], QueryPlmPackageList method [Windows Debugging], IDebugPlmClient3 interface, QueryPlmPackageList,IDebugPlmClient3.QueryPlmPackageList, dbgeng/IDebugPlmClient3::QueryPlmPackageList, debugger.idebugplmclient3_queryplmpackagelist
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
-	IDebugPlmClient3.QueryPlmPackageList
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# QueryPlmPackageList method
Query a Process Lifecycle Management (PLM) package list.

## Syntax

````
HRESULT QueryPlmPackageList(
  [in] ULONG64              Server,
  [in] PDEBUG_OUTPUT_STREAM Stream
);
````

## Parameters

`Server`

The server of the package.

`Stream`

A pointer to an output stream for results.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugplmclient3.md">IDebugPlmClient3</a>