---
UID: NF.vmbuskernelmodeclientlibapi.VmbChannelInitSetClientContextSize
title: VmbChannelInitSetClientContextSize function
author: windows-driver-content
description: The VmbChannelInitSetClientContextSize function sets the size of the optional context area allocated for the client driver on each incoming packet.
old-location: netvista\vmbchannelinitsetclientcontextsize.htm
old-project: netvista
ms.assetid: 6AABB3EB-F61A-40DA-BA9F-2AB91FC4B89E
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VmbChannelInitSetClientContextSize
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
req.alt-api: VmbChannelInitSetClientContextSize
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

# VmbChannelInitSetClientContextSize function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]
The <b>VmbChannelInitSetClientContextSize</b> function sets the size of the optional context area allocated for the client driver
on each incoming packet.


## -syntax

````
NTSTATUS
 VmbChannelInitSetClientContextSize(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     ContextSize
);
````


## -parameters

### -param Channel [in]

A handle for a channel.

### -param ContextSize [in]

The size of the context area allocated on each packet     object.

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