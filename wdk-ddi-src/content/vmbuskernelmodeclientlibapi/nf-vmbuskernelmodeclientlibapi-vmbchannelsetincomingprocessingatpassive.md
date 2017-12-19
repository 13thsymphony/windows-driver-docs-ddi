---
UID: NF.vmbuskernelmodeclientlibapi.VmbChannelSetIncomingProcessingAtPassive
title: VmbChannelSetIncomingProcessingAtPassive function
author: windows-driver-content
description: The VmbChannelSetIncomingProcessingAtPassive function sets the required IRQL for incoming parsing routines for a channel to PASSIVE_LEVEL.
old-location: netvista\vmbchannelsetincomingprocessingatpassive.htm
old-project: NetVista
ms.assetid: D8677CD9-46CB-41AB-8F05-418A31468C07
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: VmbChannelSetIncomingProcessingAtPassive
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
req.alt-api: VmbChannelSetIncomingProcessingAtPassive
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
req.product: Windows 10 or later.
---

# VmbChannelSetIncomingProcessingAtPassive function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSetIncomingProcessingAtPassive</b> function sets the required IRQL for incoming parsing routines for a channel to
PASSIVE_LEVEL.



## -syntax

````
VOID VmbChannelSetIncomingProcessingAtPassive(
  _In_ VMBCHANNEL Channel,
  _In_ BOOLEAN    RequirePassive
);
````


## -parameters

### -param Channel [in]

A handle for a channel.  



### -param RequirePassive [in]

If true, the channel requires PASSIVE_LEVEL. If false, packets may arrive at either DISPATCH_LEVEL or PASSIVE_LEVEL.


## -returns
This function does not return a value.


## -remarks


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