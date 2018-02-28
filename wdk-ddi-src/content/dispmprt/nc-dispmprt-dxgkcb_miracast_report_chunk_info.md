---
UID: NC:dispmprt.DXGKCB_MIRACAST_REPORT_CHUNK_INFO
title: DXGKCB_MIRACAST_REPORT_CHUNK_INFO
author: windows-driver-content
description: Called by the display miniport driver to report info about an encode chunk.
old-location: display\dxgkcbreportchunkinfo.htm
old-project: display
ms.assetid: 94A99749-EF80-4593-B03C-54A7AA2BDFC8
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
product: Windows
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

A driver-supplied handle to the Miracast display device. This handle was originally passed in the <b>MiracastHandle</b> member of the <a href="..\dispmprt\ns-dispmprt-_dxgk_miracast_display_callbacks.md">DXGK_MIRACAST_DISPLAY_CALLBACKS</a> structure in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a> function.

`*pChunkInfo`

A pointer to a <a href="..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_info.md">DXGK_MIRACAST_CHUNK_INFO</a> structure that contains chunk information that is to be reported by the display miniport driver.

`pPrivateDriverData`

Reserved for system use. Must be set to <b>NULL</b>.

`PrivateDataDriverSize`

Reserved for system use. Must be set to zero.


## Return Value

Returns <b>STATUS_SUCCESS</b> if it successfully delivers the message. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.

## Remarks

The display miniport driver  calls this function when it wants to report chunk info to the operating system but won't create a chunk packet that will be queued in kernel mode and retrieved by the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn_get_next_chunk_data.md">GetNextChunkData</a> function.  This call only logs Event Tracing for Windows (ETW) events and takes no other action.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | Can be called at any IRQL level. |

## See Also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_get_next_chunk_data.md">GetNextChunkData</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a>



<a href="..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_info.md">DXGK_MIRACAST_CHUNK_INFO</a>



<a href="..\dispmprt\ns-dispmprt-_dxgk_miracast_display_callbacks.md">DXGK_MIRACAST_DISPLAY_CALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_MIRACAST_REPORT_CHUNK_INFO callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>