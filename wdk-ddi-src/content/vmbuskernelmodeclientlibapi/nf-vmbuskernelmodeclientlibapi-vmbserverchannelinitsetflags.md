---
UID: NF:vmbuskernelmodeclientlibapi.VmbServerChannelInitSetFlags
title: VmbServerChannelInitSetFlags function
author: windows-driver-content
description: The VmbServerChannelInitSetFlags function sets flags unique to server channel endpoints.
old-location: netvista\vmbserverchannelinitsetflags.htm
old-project: netvista
ms.assetid: F6DBD055-8B6F-4B2B-B584-3C06979DD6DF
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.vmbserverchannelinitsetflags, VmbServerChannelInitSetFlags, vmbuskernelmodeclientlibapi/VmbServerChannelInitSetFlags, VmbServerChannelInitSetFlags function [Network Drivers Starting with Windows Vista]
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	VmbusKernelModeClientLibApi.h
apiname:
-	VmbServerChannelInitSetFlags
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbServerChannelInitSetFlags function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbServerChannelInitSetFlags</b> function sets flags unique to server channel endpoints.

## Syntax

````
NTSTATUS VmbServerChannelInitSetFlags(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     Flags
);
````

## Parameters

`Channel`

A handle for a channel.

`Flags`

A collection of bit flags to set.


## Return Value

<b>VmbServerChannelInitSetFlags</b> returns the following status values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The <i>Flags</i> value has invalid bits set.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | NtosKrnl.exe |