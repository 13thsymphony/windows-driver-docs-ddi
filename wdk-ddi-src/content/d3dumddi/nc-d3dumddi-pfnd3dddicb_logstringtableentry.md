---
UID: NC:d3dumddi.PFND3DDDICB_LOGSTRINGTABLEENTRY
title: PFND3DDDICB_LOGSTRINGTABLEENTRY
author: windows-driver-content
description: Locates a string table entry that is used by the LogMarkerStringTable function to log an Event Tracing for Windows (ETW) marker event. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.
old-location: display\logmarkerstringtableentry.htm
old-project: display
ms.assetid: 54D1F822-2D82-498D-A50F-A917FA127496
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: LogMarkerStringTableEntry, LogMarkerStringTableEntry callback function [Display Devices], PFND3DDDICB_LOGSTRINGTABLEENTRY, d3dumddi/LogMarkerStringTableEntry, display.logmarkerstringtableentry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
-	UserDefined
api_location:
-	D3dumddi.h
api_name:
-	LogMarkerStringTableEntry
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDICB_LOGSTRINGTABLEENTRY callback function
Locates a string table entry that is used by the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_logstringtable.md">LogMarkerStringTable</a> function to log an Event Tracing for Windows (ETW) marker event. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.

## Syntax

```
PFND3DDDICB_LOGSTRINGTABLEENTRY Pfnd3dddicbLogstringtableentry;

HRESULT Pfnd3dddicbLogstringtableentry(
  HANDLE hLog,
  UINT StringIndex,
  LPCWSTR Info
)
{...}
```

## Parameters

`hLog`

A handle to the ETW log that is to be written to. Must be the same <i>hLog</i> handle passed to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_logstringtable.md">LogMarkerStringTable</a> function.

`StringIndex`

The offset, in bytes, of the string table entry pointed to by <b>Info</b>. Can be negative if the string is passed along with the marker event.

`Info`

A custom text string embedded in the ETW packet. Can be <b>NULL</b>.


## Return Value

Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1,WDDM 1.3 and later Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_logstringtable.md">LogMarkerStringTable</a>