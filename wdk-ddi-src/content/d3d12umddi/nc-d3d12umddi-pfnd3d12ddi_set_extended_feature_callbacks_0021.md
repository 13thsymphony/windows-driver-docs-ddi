---
UID: NC.d3d12umddi.PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021
title: PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021
author: windows-driver-content
description: The pfnSetExtendedFeatureCallbacks callback function sets extended feature callbacks.
old-location: display\pfnd3d12ddi_set_extended_feature_callbacks_0021.htm
old-project: display
ms.assetid: 8380C972-D5A0-46D5-B32B-C31D5113BB95
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnSetExtendedFeatureCallbacks
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

# PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021 callback



## -description
The <i>pfnSetExtendedFeatureCallbacks</i> callback function sets extended feature callbacks.



## -prototype

````
PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021 pfnSetExtendedFeatureCallbacks;

VOID APIENTRY* pfnSetExtendedFeatureCallbacks(
       D3D12DDI_HDEVICE              hDevice,
       D3D12DDI_TABLE_TYPE           Table,
  _In_ _reads_(TableSize) const void *pTable,
       SIZE_T                        TableSize
)
{ ... }
````


## -parameters

### -param hDevice 

The handle of a device.


### -param Table 

A value for an implementation of video.


### -param pTable [in]

A pointer to a table value.


### -param TableSize 

The size of the table. 


## -returns
This callback function does not return a value.


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