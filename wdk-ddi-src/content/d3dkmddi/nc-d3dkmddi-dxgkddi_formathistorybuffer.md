---
UID: NC:d3dkmddi.DXGKDDI_FORMATHISTORYBUFFER
title: DXGKDDI_FORMATHISTORYBUFFER
author: windows-driver-content
description: Copies unformatted data from the history buffer into a buffer that's properly formatted to be submitted to the Event Tracing for Windows (ETW) facility.
old-location: display\dxgkddiformathistorybuffer.htm
old-project: display
ms.assetid: 84417629-5C12-4CB5-B147-0A558A4F9090
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_FORMATHISTORYBUFFER, DxgkDdiFormatHistoryBuffer, DxgkDdiFormatHistoryBuffer callback function [Display Devices], d3dkmddi/DxgkDdiFormatHistoryBuffer, display.dxgkddiformathistorybuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkDdiFormatHistoryBuffer
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_FORMATHISTORYBUFFER callback function
Copies unformatted data from the history buffer into a buffer that's properly formatted to be submitted to the Event Tracing for Windows (ETW) facility.

## Syntax

```
DXGKDDI_FORMATHISTORYBUFFER DxgkddiFormathistorybuffer;

NTSTATUS DxgkddiFormathistorybuffer(
  IN_CONST_HANDLE hContext,
  IN DXGKARG_FORMATHISTORYBUFFER * pFormatData
)
{...}
```

## Parameters

`hContext`

A handle to the device context for the DMA buffer that contains the unformatted history buffer.

`pFormatData`

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_formathistorybuffer.md">DXGKARG_FORMATHISTORYBUFFER</a> structure that contains data about how to format the history buffer.


## Return Value

Returns <b>STATUS_SUCCESS</b> if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1,WDDM 1.3 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_formathistorybuffer.md">DXGKARG_FORMATHISTORYBUFFER</a>