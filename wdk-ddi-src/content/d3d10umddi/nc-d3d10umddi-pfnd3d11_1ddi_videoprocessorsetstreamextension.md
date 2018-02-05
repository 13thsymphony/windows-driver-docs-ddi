---
UID : NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION
title : PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION
author : windows-driver-content
description : Sets the private state data for a video processor stream from an application.
old-location : display\videoprocessorsetstreamextension.htm
old-project : display
ms.assetid : 380f7fbd-34aa-401b-a7dc-5d8b521f7948
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.videoprocessorsetstreamextension, pfnVideoProcessorSetStreamExtension callback function [Display Devices], pfnVideoProcessorSetStreamExtension, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION, d3d10umddi/pfnVideoProcessorSetStreamExtension
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
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
req.typenames : "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION callback function
Sets the private state data for a video processor stream from an application.

## Syntax

```
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION Pfnd3d111DdiVideoprocessorsetstreamextension;

HRESULT Pfnd3d111DdiVideoprocessorsetstreamextension(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HVIDEOPROCESSOR,
   UINT,
  CONST GUID *,
   UINT,
  void *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11_1DDI_HVIDEOPROCESSOR`



`UINT`



`*`



`UINT`



`*`




## Return Value

<b>VideoProcessorSetStreamExtension</b> returns one of the following values:
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
The private state data was set successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was removed.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">

        The display miniport driver cannot set the requested private state data for the video processor.

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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>