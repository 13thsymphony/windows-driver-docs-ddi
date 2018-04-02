---
UID: NC:dispmprt.DXGKCB_MIRACAST_REPORT_CHUNK_INFO
title: DXGKCB_MIRACAST_REPORT_CHUNK_INFO
author: windows-driver-content
description: Called by the display miniport driver to report info about an encode chunk.
old-location: display\dxgkcbreportchunkinfo.htm
old-project: display
ms.assetid: 94A99749-EF80-4593-B03C-54A7AA2BDFC8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKCB_MIRACAST_REPORT_CHUNK_INFO, DxgkCbReportChunkInfo, DxgkCbReportChunkInfo callback function [Display Devices], display.dxgkcbreportchunkinfo, dispmprt/DxgkCbReportChunkInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
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
req.irql: Can be called at any IRQL level.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Dispmprt.h
api_name:
-	DxgkCbReportChunkInfo
product:
- Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGKCB_MIRACAST_REPORT_CHUNK_INFO callback function
Called by the display miniport driver to report info about an encode chunk.

## Syntax

```
DXGKCB_MIRACAST_REPORT_CHUNK_INFO DxgkcbMiracastReportChunkInfo;

NTSTATUS DxgkcbMiracastReportChunkInfo(
  HANDLE MiracastHandle,
  DXGK_MIRACAST_CHUNK_INFO *pChunkInfo,
  PVOID pPrivateDriverData,
  UINT PrivateDataDriverSize
)
{...}
```

## Parameters

`MiracastHandle`

A driver-supplied handle to the Miracast display device. This handle was originally passed in the <b>MiracastHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn344648">DXGK_MIRACAST_DISPLAY_CALLBACKS</a> structure in a call to the <a href="https://msdn.microsoft.com/BFF952CE-AA0F-4622-BBFC-946A45859FB7">DxgkDdiMiracastCreateContext</a> function.

`*pChunkInfo`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn322056">DXGK_MIRACAST_CHUNK_INFO</a> structure that contains chunk information that is to be reported by the display miniport driver.

`pPrivateDriverData`

Reserved for system use. Must be set to <b>NULL</b>.

`PrivateDataDriverSize`

Reserved for system use. Must be set to zero.


## Return Value

Returns <b>STATUS_SUCCESS</b> if it successfully delivers the message. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.

## Remarks

The display miniport driver  calls this function when it wants to report chunk info to the operating system but won't create a chunk packet that will be queued in kernel mode and retrieved by the user-mode <a href="https://msdn.microsoft.com/24b1d89a-4200-41ec-aa73-15b37e4cca6d">GetNextChunkData</a> function.  This call only logs Event Tracing for Windows (ETW) events and takes no other action.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | Can be called at any IRQL level. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn322056">DXGK_MIRACAST_CHUNK_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn344648">DXGK_MIRACAST_DISPLAY_CALLBACKS</a>



<a href="https://msdn.microsoft.com/BFF952CE-AA0F-4622-BBFC-946A45859FB7">DxgkDdiMiracastCreateContext</a>



<a href="https://msdn.microsoft.com/24b1d89a-4200-41ec-aa73-15b37e4cca6d">GetNextChunkData</a>