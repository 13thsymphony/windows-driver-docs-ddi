---
UID : NC:d3dumddi.PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
title : PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
author : windows-driver-content
description : The GetVideoProcessStreamStatePrivate function retrieves the private stream-state data for a video processor.
old-location : display\getvideoprocessstreamstateprivate.htm
old-project : display
ms.assetid : 0503b382-8ed3-461e-906f-27953ac5f757
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.getvideoprocessstreamstateprivate, GetVideoProcessStreamStatePrivate callback function [Display Devices], GetVideoProcessStreamStatePrivate, PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, d3dumddi/GetVideoProcessStreamStatePrivate, UserModeDisplayDriver_Functions_1016a4a3-3988-40ef-9ef9-f62a20651aaa.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Desktop
req.target-min-winverclnt : GetVideoProcessStreamStatePrivate is supported beginning with the Windows 7 operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_PTE
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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_getvideoprocessstreamstateprivate.md">D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>