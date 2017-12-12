---
UID: NC.d3dumddi.PFND3DDDI_CREATEPAGINGQUEUECB
title: PFND3DDDI_CREATEPAGINGQUEUECB
author: windows-driver-content
description: pfnCreatePagingQueueCb is used to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.
old-location: display\pfncreatepagingqueuecb.htm
old-project: display
ms.assetid: 99E4CFCF-7A0A-43A9-9E23-B7A9F9375690
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnCreatePagingQueueCb
req.alt-loc: d3dumddi.h
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

# PFND3DDDI_CREATEPAGINGQUEUECB callback



## -description
<b>pfnCreatePagingQueueCb</b> is used to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.



## -prototype

````
PFND3DDDI_CREATEPAGINGQUEUECB pfnCreatePagingQueueCb;

HRESULT APIENTRY CALLBACK* pfnCreatePagingQueueCb(
  _In_  HANDLE                     hDevice,
  _Out_ D3DDDICB_CREATEPAGINGQUEUE *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device.


### -param pData [out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicb_createpagingqueue.md">D3DDDICB_CREATEPAGINGQUEUE</a> structure that provides the details of the requested operation.




## -returns
If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
A device can have multiple paging queues created for it. Paging queues can be destroyed either explicitly by calling <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroypagingqueuecb.md">pfnDestroyPagingQueueCb</a>, or by implicitly destroying the device they belong to. After the latter, paging queue handles will become invalid.


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
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>