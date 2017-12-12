---
UID: NS.D3D12UMDDI.D3D12DDI_DEVICE_FUNCS_CORE_VIDEO_0020
title: D3D12DDI_DEVICE_FUNCS_CORE_VIDEO_0020
author: windows-driver-content
description: This structure contains device functions for core features in video.
old-location: display\d3d12ddi_device_funcs_core_video_0020.htm
old-project: display
ms.assetid: E880F758-A872-4B59-BF7D-602C3ACDA490
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D12DDI_DEVICE_FUNCS_CORE_VIDEO_0020, D3D12DDI_DEVICE_FUNCS_CORE_VIDEO_0020
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_DEVICE_FUNCS_CORE_VIDEO_0020
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

# D3D12DDI_DEVICE_FUNCS_CORE_VIDEO_0020 structure



## -description
This structure contains device functions for core features in  video.



## -syntax

````
typedef struct _D3D12DDI_DEVICE_FUNCS_CORE_VIDEO_0020 {
  PFND3D12DDI_GETPAGEABLESIZE_0020 pfnGetPageableSize;
} D3D12DDI_DEVICE_FUNCS_CORE_VIDEO_0020;
````


## -struct-fields

### -field pfnGetPageableSize

A pointer for a callback function to get pageable size. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>