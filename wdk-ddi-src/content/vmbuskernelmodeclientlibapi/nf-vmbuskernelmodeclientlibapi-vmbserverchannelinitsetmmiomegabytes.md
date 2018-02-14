---
UID: NF:vmbuskernelmodeclientlibapi.VmbServerChannelInitSetMmioMegabytes
title: VmbServerChannelInitSetMmioMegabytes function
author: windows-driver-content
description: The VmbServerChannelInitSetMmioMegabytes function specifies the amount, in megabytes, of guest memory-mapped I/O (MMIO) space to reserve for the device.
old-location: netvista\vmbserverchannelinitsetmmiomegabytes.htm
old-project: netvista
ms.assetid: 9E19BCC0-5529-470C-BF69-521FEFA3303E
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.vmbserverchannelinitsetmmiomegabytes, VmbServerChannelInitSetMmioMegabytes, vmbuskernelmodeclientlibapi/VmbServerChannelInitSetMmioMegabytes, VmbServerChannelInitSetMmioMegabytes function [Network Drivers Starting with Windows Vista]
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
-	VmbServerChannelInitSetMmioMegabytes
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbServerChannelInitSetMmioMegabytes function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbServerChannelInitSetMmioMegabytes</b> function specifies the amount, in
megabytes, of guest memory-mapped I/O (MMIO) space to reserve for the device.

## Syntax

````
NTSTATUS VmbServerChannelInitSetMmioMegabytes(
  _In_ VMBCHANNEL         Channel,
  _In_ range_(>,0) UINT16 MmioMegabytes,
  _In_ UINT16             MmioMegabytesOptional
);
````

## Parameters

`Channel`

A handle for a channel.

`MmioMegabytes`

The amount of MMIO space, in megabytes, to reserve.

`MmioMegabytesOptional`

The amount of extra optional MMIO
space, in megabytes, to reserve.


## Return Value

<b>VmbServerChannelInitSetMmioMegabytes</b> returns the following status values: 

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
 Both <i>MmioMegabytes</i> and <i>MmioMegabytesOptional</i> have a value of zero (0). One of these parameters must be greater than zero 

</td>
</tr>
</table>

## Remarks

This function exists as a convenience for driver creators.
Everything it does could be done by interacting the with the guest plug-and-play
manager and requesting memory-mapped I/O space directly.  It is
a common requirement that the Windows and Linux VMBus drivers have
the capacity to reserve MMIO space on behalf of the client.  This function allows the
server endpoint to suggest the right amount of MMIO space to reserve.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | NtosKrnl.exe |