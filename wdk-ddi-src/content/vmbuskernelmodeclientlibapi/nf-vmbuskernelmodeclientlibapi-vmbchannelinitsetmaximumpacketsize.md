---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetMaximumPacketSize
title: VmbChannelInitSetMaximumPacketSize function
author: windows-driver-content
description: The VmbChannelInitSetMaximumPacketSize function sets the maximum packet size that can be delivered through a channel, which is the maximum size that will ever be specified by the VmbPacketSend function.
old-location: netvista\vmbchannelinitsetmaximumpacketsize.htm
old-project: netvista
ms.assetid: E1CD6911-A54F-4B24-B9BE-59EF9F2C30E5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.vmbchannelinitsetmaximumpacketsize, VmbChannelInitSetMaximumPacketSize function [Network Drivers Starting with Windows Vista], vmbuskernelmodeclientlibapi/VmbChannelInitSetMaximumPacketSize, VmbChannelInitSetMaximumPacketSize
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	vmbkmcl.lib
-	vmbkmcl.dll
apiname:
-	VmbChannelInitSetMaximumPacketSize
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product: Windows 10 or later.
---


# VmbChannelInitSetMaximumPacketSize function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The  <b>VmbChannelInitSetMaximumPacketSize</b> function sets the maximum packet size that can be delivered through a channel, which is the maximum size that will ever be specified by the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md">VmbPacketSend</a> function.

## Syntax

````
NTSTATUS VmbChannelInitSetMaximumPacketSize(
  _In_ VMBCHANNEL         Channel,
  _In_ range_(>,0) UINT32 PacketSize
);
````

## Parameters

`Channel`

A handle for the channel.

`PacketSize`

Maximum size, in bytes, of a packet.


## Return Value

<b>VmbChannelInitSetMaximumPacketSize</b> returns one of the following status values: 
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
The <i>PacketSize</i> value is invalid. Zero (0) is invalid.

</td>
</tr>
</table>

## Remarks

This function can only be called during channel initialization. 

The size of
the ring buffers is, in part, based on this maximum packet size.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | Vmbkmcl.lib |

## See Also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md">VmbPacketSend</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelInitSetMaximumPacketSize function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>