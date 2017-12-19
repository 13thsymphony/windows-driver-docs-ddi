---
UID: NC.d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021
title: PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021
author: windows-driver-content
description: The pfnCalcPrivateVideoDecoderSize callback function calculates the size of a private video decoder.
old-location: display\pfnd3d12ddi_calcprivatevideodecodersize.htm
old-project: display
ms.assetid: 29A0CB0F-3469-4EF5-8C5B-132321F6C8E8
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
req.alt-api: pfnCalcPrivateVideoDecoderSize
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

# PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021 callback



## -description
The <i>pfnCalcPrivateVideoDecoderSize</i> callback function calculates the size of a private video decoder.



## -prototype

````
PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021 pfnCalcPrivateVideoDecoderSize;

SIZE_T APIENTRY* pfnCalcPrivateVideoDecoderSize(
             D3D12DDI_HDEVICE                  hDevice,
  _In_ const D3D12DDIARG_CREATE_VIDEO_DECODER  *CreateVideoDecoder
)
{ ... }
````


## -parameters

### -param hDevice 

The handle of a device. 


### -param CreateVideoDecoder [in]

The arguments used to create a video decoder.


## -remarks
The runtime allocates memory for storing the driver CPU object that represents the video decoder.  This method is used to calculate the driver object size.


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