---
UID: NC.d3d12umddi.PFND3D12DDI_CREATECRYPTOSESSION_0030
title: PFND3D12DDI_CREATECRYPTOSESSION_0030
author: windows-driver-content
description: Used to create a crypto session.
old-location: display\pfnd3d12ddi_createcryptosession_0030.htm
old-project: display
ms.assetid: 3AA323B1-C4A3-4630-A664-69FB3E5C6456
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
req.alt-api: PFND3D12DDI_CREATECRYPTOSESSION_0030
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
---

# PFND3D12DDI_CREATECRYPTOSESSION_0030 callback



## -description
Used to create a crypto session.



## -prototype

````
HRESULT APIENTRY* PFND3D12DDI_CREATECRYPTOSESSION_0030(
             D3D12DDI_HDEVICE                       hDrvDevice,
  _In_ const D3D12DDIARG_CREATE_CRYPTO_SESSION_0030 *pArgs,
             D3D12DDI_HCRYPTOSESSION_0030           hDrvCryptoSession,
             D3D12DDI_HRTPROTECTEDSESSION_0030      hRtProtectedSession
);
````


## -parameters

### -param hDrvDevice 

The hardware device being processed.


### -param pArgs [in]

The arguments used to create a crypto session.


### -param hDrvCryptoSession 

Used to create a crypto session.


### -param hRtProtectedSession 

Used to create a protected session.


## -returns
Returns STATUS_SUCCESS if completed successfully.


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