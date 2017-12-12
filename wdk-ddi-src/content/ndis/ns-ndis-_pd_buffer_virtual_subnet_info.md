---
UID: NS.NDIS._PD_BUFFER_VIRTUAL_SUBNET_INFO
title: _PD_BUFFER_VIRTUAL_SUBNET_INFO
author: windows-driver-content
description: This structure contains the virtual subnet information.
old-location: netvista\pd_buffer_virtual_subnet_info.htm
old-project: netvista
ms.assetid: 569424A2-4279-4758-A6F1-402D25F9B04F
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _PD_BUFFER_VIRTUAL_SUBNET_INFO, PD_BUFFER_VIRTUAL_SUBNET_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PD_BUFFER_VIRTUAL_SUBNET_INFO
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
---

# _PD_BUFFER_VIRTUAL_SUBNET_INFO structure



## -description
This structure contains the virtual subnet information.



## -syntax

````
typedef struct _PD_BUFFER_VIRTUAL_SUBNET_INFO {
  UINT32 VirtualSubnetId  :24;
  UINT32 Reserved  :8;
} PD_BUFFER_VIRTUAL_SUBNET_INFO, *PPD_BUFFER_VIRTUAL_SUBNET_INFO;
````


## -struct-fields

### -field VirtualSubnetId

The virtual subnet ID.


### -field Reserved

Reserved.


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
<dt>Ndis.h</dt>
</dl>
</td>
</tr>
</table>