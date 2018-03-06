---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
title: PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
author: windows-driver-content
description: The GetVideoProcessBltStatePrivate function retrieves the state data of a private bit-block transfer (bitblt) for a video processor.
old-location: display\getvideoprocessbltstateprivate.htm
old-project: display
ms.assetid: bb4c04cf-0125-47bf-8fc8-88d807e7b6ad
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetVideoProcessBltStatePrivate, GetVideoProcessBltStatePrivate callback function [Display Devices], PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE, UserModeDisplayDriver_Functions_e39248ae-aa92-4c0a-aebc-a48f7d1e24a7.xml, d3dumddi/GetVideoProcessBltStatePrivate, display.getvideoprocessbltstateprivate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetVideoProcessBltStatePrivate is supported beginning with the Windows 7 operating system.
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
-	GetVideoProcessBltStatePrivate
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE callback function
The <i>GetVideoProcessBltStatePrivate</i> function retrieves the state data of a private bit-block transfer (bitblt) for a video processor.

## Syntax

```
PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE Pfnd3dddiDxvahdGetvideoprocessbltstateprivate;

HRESULT Pfnd3dddiDxvahdGetvideoprocessbltstateprivate(
   HANDLE,
  D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE *
)
{...}
```

## Parameters

`HANDLE`



`*`




## Return Value

The <i>GetVideoProcessBltStatePrivate</i> function returns one of the following values:

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
The bitblt state data is successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetVideoProcessBltStatePrivate</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | GetVideoProcessBltStatePrivate is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_getvideoprocessbltstateprivate.md">D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>