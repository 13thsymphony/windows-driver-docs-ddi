---
UID: NC:d3dkmddi.DXGKDDI_ESCAPE
title: DXGKDDI_ESCAPE function
author: windows-driver-content
description: The DxgkDdiEscape function shares information with the user-mode display driver.
old-location: display\dxgkddiescape.htm
old-project: display
ms.assetid: 79a524cd-dec1-4ea8-a660-d9d9c644e162
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_ESCAPE
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
req.alt-api: DxgkDdiEscape
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

# DXGKDDI_ESCAPE function



## -description
The <i>DxgkDdiEscape</i> function shares information with the user-mode display driver.



## -syntax

````
DXGKDDI_ESCAPE DxgkDdiEscape;

NTSTATUS APIENTRY DxgkDdiEscape(
  _In_ const HANDLE         hAdapter,
  _In_ const DXGKARG_ESCAPE *pEscape
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pEscape [in]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_escape.md">DXGKARG_ESCAPE</a> structure that contains information about the shared information.

<div class="alert"><b>Note</b>  In order for the <b>DxgkDdiEscape</b> call to be made under the second level, the <b>HardwareAccess</b> flag must be set within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544541">D3DDDI_ESCAPEFLAGS</a> structure that is a member of <i>DXGKARG_ESCAPE</i>. If this flag is not set, then the call will fail.</div>
<div> </div>

## -returns
<i>DxgkDdiEscape</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><i>DxgkDdiEscape</i> successfully shared information.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters that were passed to <i>DxgkDdiEscape</i> contained errors that prevented it from completing.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl><i>DxgkDdiEscape</i> could not allocate memory that was required for it to complete.
<dl>
<dt><b>STATUS_PRIVILEGED_INSTRUCTION</b></dt>
</dl><i>DxgkDdiEscape</i> detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current central processing unit [CPU] process).
<dl>
<dt><b>STATUS_ILLEGAL_INSTRUCTION</b></dt>
</dl><i>DxgkDdiEscape</i> detected instructions that graphics hardware could not support.
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiEscape</i>. 

 


## -remarks
The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiEscape</i> function whenever the user-mode display driver must share information with the display miniport driver in a way that is not supported through other driver communications. 

<i>DxgkDdiEscape</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_escape.md">DXGKARG_ESCAPE</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_ESCAPE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

