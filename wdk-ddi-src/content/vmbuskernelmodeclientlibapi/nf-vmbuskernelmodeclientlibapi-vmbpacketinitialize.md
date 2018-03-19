---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketInitialize
title: VmbPacketInitialize function
author: windows-driver-content
description: The VmbPacketInitialize function initializes a buffer to contain a VMBus packet.
old-location: netvista\vmbpacketinitialize.htm
old-project: netvista
ms.assetid: D5D8D994-0BB6-44FC-A696-F2E0264445C1
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: VmbPacketInitialize, VmbPacketInitialize function [Network Drivers Starting with Windows Vista], netvista.vmbpacketinitialize, vmbuskernelmodeclientlibapi/VmbPacketInitialize
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
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbPacketInitialize
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbPacketInitialize function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketInitialize</b> function initializes a buffer to contain a VMBus packet.

## Syntax

````
NTSTATUS
 VmbPacketInitialize(
  _In_  VMBCHANNEL                         Channel,
  _Out_ writes_bytes_(ByteCount) VMBPACKET VmbPacket,
  _In_  UINT32                             ByteCount
);
````

## Parameters

`Channel`

A handle for a channel.

`VmbPacket`

The buffer to use to store the VMBus packet.

`ByteCount`

The size of <i>Buffer</i>, in bytes.


## Return Value

<b>VmbPacketInitialize</b> returns the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
 The function finished successfully.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
The value of  <i>ByteCount</i> is not valid. It needs to be greater than the maximum packet size plus the size of a void pointer. 

</td>
</tr>
</table>

## Remarks

The size of the buffer must be at
least the size calculated by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsizeofpacket.md">VmbChannelSizeofPacket</a> function.  

<b>VmbPacketInitialize</b> is  an alternative
to the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketallocate.md">VmbPacketAllocate</a> function. Use the current function if the caller supplies the
memory for the packet object. 

The packet's initial completion routine is invalid and must be set before
sending the packet.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | Vmbkmcl.lib |

## See Also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsizeofpacket.md">VmbChannelSizeofPacket</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketallocate.md">VmbPacketAllocate</a>