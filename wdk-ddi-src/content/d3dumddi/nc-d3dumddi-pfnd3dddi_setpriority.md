---
UID: NC:d3dumddi.PFND3DDDI_SETPRIORITY
title: PFND3DDDI_SETPRIORITY
author: windows-driver-content
description: The SetPriority function sets the eviction-from-memory priority for a managed texture.
old-location: display\setpriority.htm
old-project: display
ms.assetid: 61ac2d28-7aed-4796-8d09-591db936013b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_SETPRIORITY, SetPriority, SetPriority callback function [Display Devices], UserModeDisplayDriver_Functions_6e8f2a2a-f88b-45b6-9c59-b942cb44664b.xml, d3dumddi/SetPriority, display.setpriority
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
-	SetPriority
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETPRIORITY callback function
The <i>SetPriority</i> function sets the eviction-from-memory priority for a managed texture.

## Syntax

```
PFND3DDDI_SETPRIORITY Pfnd3dddiSetpriority;

HRESULT Pfnd3dddiSetpriority(
  HANDLE hDevice,
  CONST D3DDDIARG_SETPRIORITY *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>SetPriority</i> returns one of the following values:

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
The priority level is successfully set.

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
</table>

## Remarks

The Microsoft Direct3D runtime calls <i>SetPriority</i> to set the priority level for a resource. The user-mode display driver should translate the resource handle that is supplied in the <b>hResource</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543345">D3DDDIARG_SETPRIORITY</a> structure that is pointed to by <i>pData</i> to an allocation handle. After the driver makes this translation, the driver should pass the resulting handle in a call to the <a href="https://msdn.microsoft.com/1812cb0f-9232-4813-9c7b-74c9fa4d03cf">pfnSetPriorityCb</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543345">D3DDDIARG_SETPRIORITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/1812cb0f-9232-4813-9c7b-74c9fa4d03cf">pfnSetPriorityCb</a>