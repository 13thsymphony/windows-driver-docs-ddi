---
UID: NC.d3dkmddi.DXGKDDI_SETPOINTERPOSITION
title: DXGKDDI_SETPOINTERPOSITION
author: windows-driver-content
description: The DxgkDdiSetPointerPosition function sets the location and visibility state of the mouse pointer.
old-location: display\dxgkddisetpointerposition.htm
old-project: display
ms.assetid: b30e4f19-068c-4ab0-a2e9-b1f57592be1c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiSetPointerPosition
req.alt-loc: d3dkmddi.h
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

# DXGKDDI_SETPOINTERPOSITION callback



## -description
The <i>DxgkDdiSetPointerPosition</i> function sets the location and visibility state of the mouse pointer.


## -prototype

````
DXGKDDI_SETPOINTERPOSITION DxgkDdiSetPointerPosition;

NTSTATUS APIENTRY DxgkDdiSetPointerPosition(
  _In_ const HANDLE                     hAdapter,
  _In_ const DXGKARG_SETPOINTERPOSITION *pSetPointerPosition
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

### -param pSetPointerPosition [in]

[in] A pointer to a <a href="display.dxgkarg_setpointerposition">DXGKARG_SETPOINTERPOSITION</a> structure that describes where and how to display the mouse pointer.

## -returns
<i>DxgkDdiSetPointerPosition</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## -remarks
The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiSetPointerPosition</i> function to set the location of the mouse pointer. The <i>DxgkDdiSetPointerPosition</i> function is called independently of all of the other display miniport driver functions. Therefore, a <i>DxgkDdiSetPointerPosition</i> thread can run simultaneously with another display miniport driver thread. However, the system ensures that <i>DxgkDdiSetPointerPosition</i> and <a href="display.dxgkddisetpointershape">DxgkDdiSetPointerShape</a> threads cannot run simultaneously. 

If you run a <i>DxgkDdiSetPointerPosition</i> thread simultaneously with another display miniport driver thread, the display miniport driver should be able to program the mouse pointer hardware independently of other activities, such as operations that send a command buffer through direct memory access (DMA) to the graphics hardware, operations that program the graphics hardware by using memory-mapped I/O (MMIO), and so on.

<i>DxgkDdiSetPointerPosition</i> can be called even if the video present network (VidPN) topology that is associated with the <b>VidPnSourceId</b> member of the <a href="display.dxgkarg_setpointerposition">DXGKARG_SETPOINTERPOSITION</a> structure that the <i>pSetPointerPosition</i> parameter points to is disabled. In this case, the driver should return STATUS_SUCCESS but should make no changes to the state of the driver or hardware.

<i>DxgkDdiSetPointerPosition</i> should be made pageable.

## -requirements
<table>
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
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
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
<a href="display.dxgkarg_setpointerposition">DXGKARG_SETPOINTERPOSITION</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="display.dxgkddisetpointershape">DxgkDdiSetPointerShape</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SETPOINTERPOSITION callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
