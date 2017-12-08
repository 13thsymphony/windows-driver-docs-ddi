---
UID: NC.d3dkmddi.DXGKCB_GETHANDLEPARENT
title: DXGKCB_GETHANDLEPARENT
author: windows-driver-content
description: The DxgkCbGetHandleParent function retrieves the parent resource from the specified allocation.
old-location: display\dxgkcbgethandleparent.htm
old-project: display
ms.assetid: db8e7a91-d62a-4d2f-ac21-266e365a352c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbGetHandleParent
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: < DISPATCH_LEVEL
---

# DXGKCB_GETHANDLEPARENT callback



## -description
The <b>DxgkCbGetHandleParent</b> function retrieves the parent resource from the specified allocation.


## -prototype

````
DXGKCB_GETHANDLEPARENT DxgkCbGetHandleParent;

D3DKMT_HANDLE APIENTRY DxgkCbGetHandleParent(
  _In_ D3DKMT_HANDLE hAllocation
)
{ ... }
````


## -parameters

### -param hAllocation [in]

[in] A handle to an allocation. This handle must be the kernel-mode handle that the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) assigned for the allocation.

## -returns
<b>DxgkCbGetHandleParent</b> returns a graphics subsystem-specific handle to the parent resource for the allocation that is associated with the handle that the <i>hAllocation</i> parameter specifies.

If <i>DxgkCbGetHandleParent</i> returns a <b>NULL</b> handle, the DirectX graphics kernel subsystem was unable to resolve the handle to the parent resource because, for example, of the following possible reasons:



If a <b>NULL</b> handle is returned, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.

## -remarks
For <b>DxgkCbGetHandleParent</b> to return a resource handle, the handle in <i>hAllocation</i> must be an allocation handle that is associated with a resource; otherwise, <b>DxgkCbGetHandleParent</b> returns <b>NULL</b>.

## -requirements
<table>
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
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt; DISPATCH_LEVEL
</td>
</tr>
</table>