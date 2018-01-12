---
UID: NS:d3dkmthk._D3DKMT_UNLOCK2
title: _D3DKMT_UNLOCK2
author: windows-driver-content
description: D3DKMT_UNLOCK2 describes an allocation to unlock.
old-location: display\d3dkmt_unlock2.htm
old-project: display
ms.assetid: 8651297B-BCF7-42A2-9175-D9D072E052D6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_UNLOCK2, D3DKMT_UNLOCK2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_UNLOCK2
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_UNLOCK2
---

# _D3DKMT_UNLOCK2 structure



## -description
<b>D3DKMT_UNLOCK2</b> describes an allocation to unlock.



## -syntax

````
typedef struct _D3DKMT_UNLOCK2 {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hAllocation;
} D3DKMT_UNLOCK2;
````


## -struct-fields

### -field hDevice

The handle to the device.


### -field hAllocation

The handle to the allocation to unlock.


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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>