---
UID: NC:d3dumddi.PFND3DDDI_GETOVERLAYCOLORCONTROLS
title: PFND3DDDI_GETOVERLAYCOLORCONTROLS
author: windows-driver-content
description: The GetOverlayColorControls function retrieves color-control settings for the given overlay.
old-location: display\getoverlaycolorcontrols.htm
old-project: display
ms.assetid: 23b15bb5-4394-406b-8869-f9d1e4e2b539
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetOverlayColorControls, GetOverlayColorControls callback function [Display Devices], PFND3DDDI_GETOVERLAYCOLORCONTROLS, UserModeDisplayDriver_Functions_b50c3637-892b-4cc9-ad9a-97feeeb649fc.xml, d3dumddi/GetOverlayColorControls, display.getoverlaycolorcontrols
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
-	GetOverlayColorControls
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_GETOVERLAYCOLORCONTROLS callback function
The <i>GetOverlayColorControls</i> function retrieves color-control settings for the given overlay.

## Syntax

```
PFND3DDDI_GETOVERLAYCOLORCONTROLS Pfnd3dddiGetoverlaycolorcontrols;

HRESULT Pfnd3dddiGetoverlaycolorcontrols(
  HANDLE hDevice,
  D3DDDIARG_GETOVERLAYCOLORCONTROLS *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>GetOverlayColorControls</i> returns one of the following values:

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
The color-control settings were successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetOverlayColorControls</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>

## Remarks

The Microsoft Direct3D runtime calls the <i>GetOverlayColorControls</i> function to return the current brightness, contrast, hue, saturation, sharpness, gamma, and color-enable settings that are associated with a specific overlay. 

The runtime can also call <i>GetOverlayColorControls</i> for an overlay that is not yet visible. In this situation, when the <b>hOverlay</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543169">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a> structure pointed to by <i>pData</i> is set to <b>NULL</b>, the driver should return the default color-control settings of the overlay hardware.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543169">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>