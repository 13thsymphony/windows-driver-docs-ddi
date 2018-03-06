---
UID: NC:d3dumddi.PFND3DDDI_VIDEOPROCESSENDFRAME
title: PFND3DDDI_VIDEOPROCESSENDFRAME
author: windows-driver-content
description: The VideoProcessEndFrame function notifies the user-mode display driver that all of the data that is required to process the current frame was submitted.
old-location: display\videoprocessendframe.htm
old-project: display
ms.assetid: a5be6834-bb27-4da0-8802-25a9ca58c101
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_VIDEOPROCESSENDFRAME, UserModeDisplayDriver_Functions_b7ef391b-90b5-49a6-880e-d0c4f287d0ad.xml, VideoProcessEndFrame, VideoProcessEndFrame callback function [Display Devices], d3dumddi/VideoProcessEndFrame, display.videoprocessendframe
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
-	VideoProcessEndFrame
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_VIDEOPROCESSENDFRAME callback function
The <i>VideoProcessEndFrame</i> function notifies the user-mode display driver that all of the data that is required to process the current frame was submitted.

## Syntax

```
PFND3DDDI_VIDEOPROCESSENDFRAME Pfnd3dddiVideoprocessendframe;

HRESULT Pfnd3dddiVideoprocessendframe(
  HANDLE hDevice,
  D3DDDIARG_VIDEOPROCESSENDFRAME *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>VideoProcessEndFrame</i> returns one of the following values:

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
Processing of the current frame is successfully completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>VideoProcessEndFrame</i> cannot allocate memory required for it to complete.

</td>
</tr>
</table>

## Remarks

The <i>VideoProcessEndFrame</i> function notifies the user-mode display driver that its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessblt.md">VideoProcessBlt</a> function can no longer be called on the specified video processing device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessblt.md">VideoProcessBlt</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessendframe.md">D3DDDIARG_VIDEOPROCESSENDFRAME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_VIDEOPROCESSENDFRAME callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>