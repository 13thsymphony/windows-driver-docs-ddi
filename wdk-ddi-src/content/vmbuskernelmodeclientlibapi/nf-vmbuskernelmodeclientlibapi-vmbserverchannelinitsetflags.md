---
UID: NF.vmbuskernelmodeclientlibapi.VmbServerChannelInitSetFlags
title: VmbServerChannelInitSetFlags
author: windows-driver-content
description: The VmbServerChannelInitSetFlags function sets flags unique to server channel endpoints.
old-location: netvista\vmbserverchannelinitsetflags.htm
old-project: netvista
ms.assetid: F6DBD055-8B6F-4B2B-B584-3C06979DD6DF
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: VmbServerChannelInitSetFlags
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
req.alt-api: VmbServerChannelInitSetFlags
req.alt-loc: VmbusKernelModeClientLibApi.h
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
req.iface: 
req.product: Windows 10 or later.
---

# VmbServerChannelInitSetFlags function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <b>VmbServerChannelInitSetFlags</b> function sets flags unique to server channel endpoints.</p>


## -syntax

````
NTSTATUS VmbServerChannelInitSetFlags(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     Flags
);
````


## -parameters
<dl>

### -param Channel [in]

<dd>
<p>A handle for a channel.  </p>
</dd>

### -param Flags [in]

<dd>
<p>A collection of bit flags to set.</p>
</dd>
</dl>

## -returns
<p><b>VmbServerChannelInitSetFlags</b> returns the following status values: </p><dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl><p>The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl><p>The <i>Flags</i> value has invalid bits set.</p>

<p> </p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.13</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
</table>