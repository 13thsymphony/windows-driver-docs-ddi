---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYPROTECTEDRESOURCESESSION_0030
title: PFND3D12DDI_DESTROYPROTECTEDRESOURCESESSION_0030
author: windows-driver-content
description: Used to destroy a protected resource session.
old-location: display\pfnd3d12ddi_destroyprotectedresourcesession_0030.htm
old-project: display
ms.assetid: B247AB7B-D133-43FE-A208-CF5E3C7F7DBE
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFND3D12DDI_DESTROYPROTECTEDRESOURCESESSION_0030
req.alt-loc: d3d12umddi.h
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
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_DESTROYPROTECTEDRESOURCESESSION_0030 callback



## -description
Used to destroy a protected resource session.



## -prototype

````
VOID APIENTRY* PFND3D12DDI_DESTROYPROTECTEDRESOURCESESSION_0030(
   D3D12DDI_HDEVICE                        hDrvDevice,
   D3D12DDI_HPROTECTEDRESOURCESESSION_0030 hDrvProtectedResourceSession
);
````


## -parameters

### -param hDrvDevice 

The hardware device being processed.


### -param hDrvProtectedResourceSession 

The protected resource session.


## -returns
This callback function does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
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