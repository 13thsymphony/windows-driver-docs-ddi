---
UID: NC.d3d12umddi.PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020
author: windows-driver-content
description: The pfnGetDecodeFormatCount callback function retrieves the number of formats supported for a decode configuration.
old-location: display\pfnd3d12ddi_video_get_decode_format_count.htm
old-project: display
ms.assetid: 84503E38-E141-4DAC-B305-6C7E6157A3E9
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnGetDecodeFormatCount
req.alt-loc: D3d12umddi.h
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
---

# PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 callback



## -description
The <i>pfnGetDecodeFormatCount</i> callback function retrieves the number of formats supported for a decode configuration.



## -prototype

````
PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 pfnGetDecodeFormatCount;

UINT APIENTRY* pfnGetDecodeFormatCount(
         D3D12DDI_HDEVICE                    hDrvDevice,
         UINT                                NodeIndex,
   const D3D12DDI_VIDEO_DECODE_CONFIGURATION *pConfiguration
)
{ ... }
````


## -parameters

### -param hDrvDevice 

The handle of the device.


### -param NodeIndex 

The physical adapter of the device to which this operation applies.


### -param pConfiguration 

The decode configuration for the list of formats.  For more information, see the <a href="display.d3d12ddi_video_decode_configuration_flags">3D12DDI_VIDEO_DECODE_CONFIGURATION</a> enumeration.


## -returns
This function retrieves the number of formats supported for a decode configuration.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3d12ddi_video_decode_configuration_flags">3D12DDI_VIDEO_DECODE_CONFIGURATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

