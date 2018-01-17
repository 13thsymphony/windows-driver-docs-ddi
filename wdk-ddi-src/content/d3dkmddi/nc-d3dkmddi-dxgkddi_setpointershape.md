---
UID: NC:d3dkmddi.DXGKDDI_SETPOINTERSHAPE
title: DXGKDDI_SETPOINTERSHAPE function
author: windows-driver-content
description: The DxgkDdiSetPointerShape function sets the appearance and location of the mouse pointer.
old-location: display\dxgkddisetpointershape.htm
old-project: display
ms.assetid: 36b462f7-5bad-4716-8138-af00d20e945b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_SETPOINTERSHAPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiSetPointerShape
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
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
---

# DXGKDDI_SETPOINTERSHAPE function



## -description
The <i>DxgkDdiSetPointerShape</i> function sets the appearance and location of the mouse pointer.



## -syntax

````
DXGKDDI_SETPOINTERSHAPE DxgkDdiSetPointerShape;

NTSTATUS APIENTRY DxgkDdiSetPointerShape(
  _In_ const HANDLE                  hAdapter,
  _In_ const DXGKARG_SETPOINTERSHAPE *pSetPointerShape
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pSetPointerShape [in]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setpointershape.md">DXGKARG_SETPOINTERSHAPE</a> structure that describes the appearance and location of the mouse pointer.


## -returns
<i>DxgkDdiSetPointerShape</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The mouse pointer is successfully drawn.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl><i>DxgkDdiSetPointerShape</i> could not allocate memory that was required for it to complete.

 


## -remarks
The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiSetPointerShape</i> function to set information about the mouse pointer. The <i>DxgkDdiSetPointerShape</i> function is called independently of all of the other display miniport driver functions. Therefore, a <i>DxgkDdiSetPointerShape</i> thread can run simultaneously with another display miniport driver thread. However, the system ensures that <i>DxgkDdiSetPointerShape</i> and <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointerposition.md">DxgkDdiSetPointerPosition</a> threads cannot run simultaneously. 

If you run a <i>DxgkDdiSetPointerShape</i> thread simultaneously with another display miniport driver thread, the display miniport driver should be able to program the mouse pointer hardware independently of other activities, such as operations that send a command buffer through direct memory access (DMA) to the graphics hardware, operations that program the graphics hardware by using memory-mapped I/O (MMIO), and so on.

<i>DxgkDdiSetPointerShape</i> is not called if the video present network (VidPN) topology that is associated with the <b>VidPnSourceId</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setpointershape.md">DXGKARG_SETPOINTERSHAPE</a> structure that the <i>pSetPointerShape</i> parameter points to is disabled.

<i>DxgkDdiSetPointerShape</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setpointershape.md">DXGKARG_SETPOINTERSHAPE</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointerposition.md">DxgkDdiSetPointerPosition</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SETPOINTERSHAPE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

