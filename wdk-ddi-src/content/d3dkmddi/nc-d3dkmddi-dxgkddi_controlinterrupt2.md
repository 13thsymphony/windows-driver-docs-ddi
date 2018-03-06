---
UID: NC:d3dkmddi.DXGKDDI_CONTROLINTERRUPT2
title: DXGKDDI_CONTROLINTERRUPT2
author: windows-driver-content
description: The DxgkDdi_ControlInterrupt2 function enables or disables the given interrupt type on the graphics hardware.
old-location: display\dxgkddicontrolinterrupt2.htm
old-project: display
ms.assetid: 0C09CAB1-3DFC-4340-8FF2-99CAF7F13156
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_CONTROLINTERRUPT2, DxgkDdi_ControlInterrupt2, DxgkDdi_ControlInterrupt2 callback function [Display Devices], d3dkmddi/DxgkDdi_ControlInterrupt2, display.dxgkddicontrolinterrupt2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 10 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdi_ControlInterrupt2
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_CONTROLINTERRUPT2 callback function
The <i>DxgkDdi_ControlInterrupt2</i> function enables or disables the given interrupt type on the graphics hardware.

## Syntax

```
DXGKDDI_CONTROLINTERRUPT2 DxgkddiControlinterrupt2;

NTSTATUS DxgkddiControlinterrupt2(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_DXGKARG_CONTROLINTERRUPT2 InterruptControl
)
{...}
```

## Parameters

`hAdapter`

[in] A handle to the adapter object for the graphics processing unit (GPU). The driver returned this handle in the <i>MiniportDeviceContext</i> parameter from a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`InterruptControl`

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_controlinterrupt2.md">DXGKARG_CONTROLINTERRUPT2</a>-type value that supplies the interrupt type, as well as the VSYNC state.


## Return Value

<i>DxgkDdi_ControlInterrupt2</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The interrupt type was successfully enabled or disabled on the graphics hardware.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt2.md">DxgkDdi_ControlInterrupt2</a> does not support enabling or disabling the specified interrupt type.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 10 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |