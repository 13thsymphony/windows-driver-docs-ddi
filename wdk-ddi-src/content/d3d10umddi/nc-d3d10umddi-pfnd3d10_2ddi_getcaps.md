---
UID: NC:d3d10umddi.PFND3D10_2DDI_GETCAPS
title: PFND3D10_2DDI_GETCAPS
author: windows-driver-content
description: The GetCaps(D3D10_2) function queries for capabilities of the graphics adapter.
old-location: display\getcaps_d3d10_2_.htm
old-project: display
ms.assetid: 83cd5f34-5f12-4ead-ad33-366fc3c6e804
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetCaps, GetCaps callback function [Display Devices], PFND3D10_2DDI_GETCAPS, UserModeDisplayDriverDx11_Functions_b0f0ebe4-205d-4eb5-ad35-e91dbcb21a1c.xml, d3d10umddi/GetCaps, display.getcaps_d3d10_2_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetCaps(D3D10_2) is supported beginning with the Windows 7 operating system.
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
-	GetCaps
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10_2DDI_GETCAPS callback function
The <i>GetCaps(D3D10_2)</i> function queries for capabilities of the graphics adapter.

## Syntax

```
PFND3D10_2DDI_GETCAPS Pfnd3d102DdiGetcaps;

HRESULT Pfnd3d102DdiGetcaps(
   D3D10DDI_HADAPTER,
  CONST D3D10_2DDIARG_GETCAPS *
)
{...}
```

## Parameters

`D3D10DDI_HADAPTER`



`*`




## Return Value

<i>GetCaps(D3D10_2)</i> returns one of the following values:

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
The capabilities are successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetCaps(D3D10_2)</i> could not allocate memory that is required for it to complete.

</td>
</tr>
</table>

## Remarks

The data that is returned by the <i>GetCaps(D3D10_2)</i> function in the <b>pData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541887">D3D10_2DDIARG_GETCAPS</a> structure depends on the type of data that is requested (that is, the data depends on the <b>Type</b> member of D3D10_2DDIARG_GETCAPS and sometimes on the <b>pInfo</b> member).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | GetCaps(D3D10_2) is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541887">D3D10_2DDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541900">D3D10_2DDI_ADAPTERFUNCS</a>