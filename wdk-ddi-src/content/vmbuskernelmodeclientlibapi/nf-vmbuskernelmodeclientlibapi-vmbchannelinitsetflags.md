---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetFlags
title: VmbChannelInitSetFlags function
author: windows-driver-content
description: The VmbChannelInitSetFlags function sets flags common to server or client channel endpoints.
old-location: netvista\vmbchannelinitsetflags.htm
old-project: netvista
ms.assetid: 12525F3C-12D6-477E-8C7D-3DE9AAA044AE
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: VmbChannelInitSetFlags
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
req.alt-api: VmbChannelInitSetFlags
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

# VmbChannelInitSetFlags function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetFlags</b> function sets flags common to server or client channel endpoints.



## -syntax

````
NTSTATUS VmbChannelInitSetFlags(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     Flags
);
````


## -parameters

### -param Channel [in]

A handle for the channel.



### -param Flags [in]

A collection of bit flags to set.


## -returns
<b>VmbChannelInitSetFlags</b> can return one of the following status values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>The value in <i>Flags</i> has invalid bits.

 


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