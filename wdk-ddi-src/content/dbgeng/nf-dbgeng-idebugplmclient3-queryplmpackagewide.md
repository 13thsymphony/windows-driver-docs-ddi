---
UID: NF:dbgeng.IDebugPlmClient3.QueryPlmPackageWide
title: IDebugPlmClient3::QueryPlmPackageWide method
author: windows-driver-content
description: Query a Process Lifecycle Management (PLM) package.
old-location: debugger\idebugplmclient3_queryplmpackagewide.htm
old-project: debugger
ms.assetid: 29BAAEF9-5B69-4723-BC23-A8B668E2A867
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugPlmClient3, IDebugPlmClient3::QueryPlmPackageWide, QueryPlmPackageWide
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
req.alt-api: IDebugPlmClient3.QueryPlmPackageWide
req.alt-loc: dbgeng.h
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugPlmClient3::QueryPlmPackageWide method



## -description
Query a Process Lifecycle Management (PLM) package.



## -syntax

````
HRESULT QueryPlmPackageWide(
  [in] ULONG64              Server,
  [in] PCWSTR               PackageFullName,
  [in] PDEBUG_OUTPUT_STREAM Stream
);
````


## -parameters

### -param Server [in]

The server of the package.


### -param PackageFullName [in]

A pointer to the package name.


### -param Stream [in]

A pointer to an output stream for results.


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugplmclient3.md">IDebugPlmClient3</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugPlmClient3::QueryPlmPackageWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

