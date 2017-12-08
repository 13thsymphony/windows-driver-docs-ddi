---
UID: NC.d3dkmddi.DXGKDDI_CANCELCOMMAND
title: DXGKDDI_CANCELCOMMAND
author: windows-driver-content
description: Cleans up internal resources associated with a direct memory access (DMA) packet that was in the GPU scheduler's software queue but never reached the hardware queue because the device went into an error state.
old-location: display\dxgkddicancelcommand.htm
old-project: display
ms.assetid: c290c313-14ee-4554-9bb1-8adec1892426
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiCancelCommand
req.alt-loc: D3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# DXGKDDI_CANCELCOMMAND callback



## -description
Cleans up internal resources associated with a direct memory access (DMA) packet that was in the GPU scheduler's software queue but  never reached the hardware queue because the device went into an error state. Such an error state is typically caused by a <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a> event.


## -prototype

````
PDXGKDDI_CANCELCOMMAND DxgkDdiCancelCommand;

_Check_return_ NTSTATUS APIENTRY* DxgkDdiCancelCommand(
  _In_ const HANDLE                hAdapter,
  _In_ const DXGKARG_CANCELCOMMAND *pCancelCommand
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

### -param pCancelCommand [in]

A pointer to a <a href="display.dxgkarg_cancelcommand">DXGKARG_CANCELCOMMAND</a> structure that specifies resources to be cleaned up after a command is removed from the hardware  queue.

## -returns
Returns <b>STATUS_SUCCESS</b> upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. For more information, see the following Remarks section.

## -remarks
If the driver returns an error code, the DirectX graphics kernel subsystem  causes a system bugcheck to occur. In a crash dump file, the error is noted by the message <b>BugCheck 0x119</b>, which has the following four parameters.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012
</td>
</tr>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgk_vidschcaps">DXGK_VIDSCHCAPS</a>
</dt>
<dt>
<a href="display.dxgkarg_cancelcommand">DXGKARG_CANCELCOMMAND</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDXGKDDI_CANCELCOMMAND callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
