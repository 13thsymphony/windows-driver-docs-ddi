---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEDEVICE
title: PFND3D10DDI_CREATEDEVICE
author: windows-driver-content
description: The CreateDevice(D3D10) function creates a graphics context that is referenced in subsequent calls.
old-location: display\createdevice_d3d10_.htm
old-project: display
ms.assetid: c69eedb1-c975-412c-aa9f-cf64a702f937
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CreateDevice, CreateDevice callback function [Display Devices], PFND3D10DDI_CREATEDEVICE, UserModeDisplayDriverDx10_Functions_4d3d9d4c-e03b-46a9-a62a-cb49f071c0a2.xml, d3d10umddi/CreateDevice, display.createdevice_d3d10_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	CreateDevice
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_CREATEDEVICE callback function
The <b>CreateDevice(D3D10)</b> function creates a graphics context that is referenced in subsequent calls.

## Syntax

```
PFND3D10DDI_CREATEDEVICE Pfnd3d10ddiCreatedevice;

HRESULT Pfnd3d10ddiCreatedevice(
   D3D10DDI_HADAPTER,
  D3D10DDIARG_CREATEDEVICE *
)
{...}
```

## Parameters

`D3D10DDI_HADAPTER`



`*`




## Return Value

<b>CreateDevice(D3D10)</b> returns one of the following values:

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
The graphics context was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DXGI_STATUS_NO_REDIRECTION</b></dt>
</dl>
</td>
<td width="60%">
The graphics context was successfully created. However, the DirectX Graphics Infrastructure (DXGI) should not use the shared resource presentation path to effect communication with the Desktop Windows Manager (DWM). For more information about the DXGI DDI, see <a href="https://msdn.microsoft.com/3a49d7cb-984f-4e4f-a549-5c0442e1c45a">Supporting the DXGI DDI</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> could not allocate the memory that was required for it to complete.

</td>
</tr>
</table>

## Remarks

A display device is a graphics context that is used to hold a collection of rendering state. The same process can create multiple devices on a given adapter. Note that the number of display devices that can simultaneously exist is limited only by available system memory. That is, a driver cannot hardcode a maximum device limit.

Generally, devices are independent of each other, so that resources that are created in one device cannot be referenced or accessed by resources that are created in another. However, cross-process resources are an exception to this rule.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541811">D3D10DDI_ADAPTERFUNCS</a>



<a href="https://msdn.microsoft.com/90ada8c8-8ad8-4992-aac1-6eb7fdf3f249">DestroyDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/50c10021-2bad-4e3c-99cc-24cf31fbc95d">OpenAdapter10</a>