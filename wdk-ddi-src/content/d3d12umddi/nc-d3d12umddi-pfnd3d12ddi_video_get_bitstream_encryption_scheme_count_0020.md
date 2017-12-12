---
UID: NC.d3d12umddi.PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020
author: windows-driver-content
description: The pfnGetBitstreamEncryptionSchemeCount callback function retrieves the number of encryption schemes supported for a decode profile.
old-location: display\pfnd3d12ddi_video_get_decode_bitstream_encryption_scheme_count.htm
old-project: display
ms.assetid: BD3DFB48-9470-45CC-93BC-A918FD43DC3F
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
req.alt-api: pfnGetBitstreamEncryptionSchemeCount
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

# PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 callback



## -description
The <i>pfnGetBitstreamEncryptionSchemeCount</i> callback function retrieves the number of encryption schemes supported for a decode profile.



## -prototype

````
PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 pfnGetBitstreamEncryptionSchemeCount;

UINT APIENTRY* pfnGetBitstreamEncryptionSchemeCount(
   D3D12DDI_HDEVICE hDrvDevice,
   UINT             NodeIndex,
   REFGUID          DecodeProfile
)
{ ... }
````


## -parameters

### -param hDrvDevice 

The handle of the device.


### -param NodeIndex 

The physical adapter of the device to which this operation applies.


### -param DecodeProfile 

The decode profile GUID to retrieve the count of supported encryption GUIDs.


## -returns
This function retrieves the number of encryption schemes supported for a decode profile.


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