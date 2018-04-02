---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
title: PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
author: windows-driver-content
description: The GetVideoProcessStreamStatePrivate function retrieves the private stream-state data for a video processor.
old-location: display\getvideoprocessstreamstateprivate.htm
old-project: display
ms.assetid: 0503b382-8ed3-461e-906f-27953ac5f757
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetVideoProcessStreamStatePrivate, GetVideoProcessStreamStatePrivate callback function [Display Devices], PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, UserModeDisplayDriver_Functions_1016a4a3-3988-40ef-9ef9-f62a20651aaa.xml, d3dumddi/GetVideoProcessStreamStatePrivate, display.getvideoprocessstreamstateprivate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetVideoProcessStreamStatePrivate is supported beginning with the Windows 7 operating system.
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
-	GetVideoProcessStreamStatePrivate
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE callback function
The <i>GetVideoProcessStreamStatePrivate</i> function retrieves the private stream-state data for a video processor.

## Syntax

```
PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE Pfnd3dddiDxvahdGetvideoprocessstreamstateprivate;

HRESULT Pfnd3dddiDxvahdGetvideoprocessstreamstateprivate(
   HANDLE,
  D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE *
)
{...}
```

## Parameters

`HANDLE`



`*`




## Return Value

The <i>GetVideoProcessStreamStatePrivate</i> function returns one of the following values:

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
The stream-state data is successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetVideoProcessStreamStatePrivate</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | GetVideoProcessStreamStatePrivate is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543089">D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE</a>