---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSetTransactionQuota
title: VmbChannelSetTransactionQuota function
author: windows-driver-content
description: The VmbChannelSetTransactionQuota function sets the incoming packet quota.
old-location: netvista\vmbchannelsettransactionquota.htm
old-project: netvista
ms.assetid: C88F03BE-96D3-46A7-8269-1ECBFA539111
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: VmbChannelSetTransactionQuota
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: VmbChannelSetTransactionQuota
req.alt-loc: vmbkmcl.lib,vmbkmcl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
req.typenames: *PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelSetTransactionQuota function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSetTransactionQuota</b> function sets the incoming packet quota. 



## -syntax

````
VOID VmbChannelSetTransactionQuota(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     Quota
);
````


## -parameters

### -param Channel [in]

A handle for a channel.  


### -param Quota [in]

 The maximum outstanding packet quota. This value must be greater than 0.


## -returns
This function does not return a value.


## -remarks
The incoming packet quota can be set to be lower than the current
outstanding packet count. In that case, no new packets are removed from
the queue until sufficient packets have been completed.


 If the queue is currently blocked due to quota, this operation does not restart it. The queue only restarts once a packet is completed.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.13

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Vmbkmcl.lib</dt>
</dl>
</td>
</tr>
</table>