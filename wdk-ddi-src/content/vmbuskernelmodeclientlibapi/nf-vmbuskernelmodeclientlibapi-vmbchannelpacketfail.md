---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelPacketFail
title: VmbChannelPacketFail function
author: windows-driver-content
description: The VmbChannelPacketFail function fails a packet during packet processing due to an unrecoverable error. This function stops the queue.
old-location: netvista\vmbchannelpacketfail.htm
old-project: netvista
ms.assetid: 177B4509-A0EC-4F71-AF21-916A7A5F06DB
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: VmbChannelPacketFail
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
req.alt-api: VmbChannelPacketFail
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

# VmbChannelPacketFail function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPacketFail</b>  function fails a packet during packet processing due to an unrecoverable error. This function stops the queue.  



## -syntax

````
VOID VmbChannelPacketFail(
  _In_ PacketCompletionContext VMBPACKETCOMPLETION
);
````


## -parameters

### -param VMBPACKETCOMPLETION [in]

A  handle that identifies the incoming packet and is used to refer to the packet
once processing is finished.  


## -returns
This function does not return a value.


## -remarks
Call this function for packets presented to the server endpoint which seem malformed, to
the extent that channel processing should cease.


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