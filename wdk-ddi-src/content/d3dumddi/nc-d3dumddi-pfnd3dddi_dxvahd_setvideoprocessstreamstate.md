---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
title: PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
author: windows-driver-content
description: The SetVideoProcessStreamState function sets the stream state for a video processor.
old-location: display\setvideoprocessstreamstate.htm
old-project: display
ms.assetid: b48fbe58-056a-4c3b-8e1e-c65515c21ee4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE, SetVideoProcessStreamState, SetVideoProcessStreamState callback function [Display Devices], UserModeDisplayDriver_Functions_3860b09d-ba06-4b9e-bf6d-65e7b90135fd.xml, d3dumddi/SetVideoProcessStreamState, display.setvideoprocessstreamstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: SetVideoProcessStreamState is supported beginning with the Windows 7 operating system.
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
-	SetVideoProcessStreamState
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE callback function
The <i>SetVideoProcessStreamState</i> function sets the stream state for a video processor.

## Syntax

```
PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE Pfnd3dddiDxvahdSetvideoprocessstreamstate;

HRESULT Pfnd3dddiDxvahdSetvideoprocessstreamstate(
   HANDLE,
  CONST D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE *
)
{...}
```

## Parameters

`HANDLE`



`*`




## Return Value

The <i>SetVideoProcessStreamState</i> function returns one of the following values:

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
The stream state is successfully set. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>SetVideoProcessStreamState</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | SetVideoProcessStreamState is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543098">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>