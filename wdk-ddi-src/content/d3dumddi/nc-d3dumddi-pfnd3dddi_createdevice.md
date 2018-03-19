---
UID: NC:d3dumddi.PFND3DDDI_CREATEDEVICE
title: PFND3DDDI_CREATEDEVICE
author: windows-driver-content
description: The CreateDevice function creates a graphics context that is referenced in subsequent calls.
old-location: display\createdevice.htm
old-project: display
ms.assetid: ce35bdac-af90-471f-af93-0e665be6c7f6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateDevice, CreateDevice callback function [Display Devices], PFND3DDDI_CREATEDEVICE, UserModeDisplayDriver_Functions_4603a980-54aa-4d90-859a-d84c2afe5f03.xml, d3dumddi/CreateDevice, display.createdevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	CreateDevice
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_CREATEDEVICE callback function
The <b>CreateDevice</b> function creates a graphics context that is referenced in subsequent calls.

## Syntax

```
PFND3DDDI_CREATEDEVICE Pfnd3dddiCreatedevice;

HRESULT Pfnd3dddiCreatedevice(
  HANDLE hAdapter,
  D3DDDIARG_CREATEDEVICE *
)
{...}
```

## Parameters

`hAdapter`

A handle that identifies the graphics adapter.

`*`




## Return Value

<b>CreateDevice</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The graphics context is successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a> could not allocate the memory that was required for it to complete.

</td>
</tr>
</table>

## Remarks

A display device is a graphics context that is used to hold a collection of rendering state. Multiple devices can be created by the same process on a given adapter. Note that the number of display devices that can simultaneously exist is limited only by available system memory. That is, a driver cannot hardcode a maximum device limit.

Generally, devices are independent of each other, so that resources that are created in one device cannot be referenced or accessed by resources that are created in another. However, cross-process resources are an exception to this rule.

When the Direct3D runtime calls <b>CreateDevice</b> to create a device, the runtime does not create a default graphics processing unit (GPU) context thread of execution for the device. The driver must explicitly call the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function to create one or more contexts as required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_adapterfuncs.md">D3DDDI_ADAPTERFUNCS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroydevice.md">DestroyDevice</a>