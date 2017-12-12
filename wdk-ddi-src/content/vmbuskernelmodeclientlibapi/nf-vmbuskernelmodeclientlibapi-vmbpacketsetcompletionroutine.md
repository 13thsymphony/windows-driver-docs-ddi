---
UID: NF.vmbuskernelmodeclientlibapi.VmbPacketSetCompletionRoutine
title: VmbPacketSetCompletionRoutine function
author: windows-driver-content
description: The VmbPacketSetCompletionRoutine function sets the completion routine for a packet object.
old-location: netvista\vmbpacketsetcompletionroutine.htm
old-project: netvista
ms.assetid: 5781FE16-6CC8-425B-B14D-C78901D81A75
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: VmbPacketSetCompletionRoutine
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
req.alt-api: VmbPacketSetCompletionRoutine
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

# VmbPacketSetCompletionRoutine function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSetCompletionRoutine</b> function sets the completion routine for a packet object.  



## -syntax

````
VOID VmbPacketSetCompletionRoutine(
  _In_ VMBPACKET                         PacketObject,
  _In_ PFN_VMB_PACKET_COMPLETION_ROUTINE CompletionRoutine
);
````


## -parameters

### -param PacketObject [in]

The packet for which to specify a completion routine.



### -param CompletionRoutine [in]

Function to call when the packet is completed.


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

## -see-also
<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_packet_completion_routine.md">EvtVmbPacketCompletionRoutine</a>
</dt>
<dt>
<a href="netvista.vmbpacketsend">VmbPacketSend</a>
</dt>
<dt>
<a href="netvista.vmbpacketsendwithexternalmdl">VmbPacketSendWithExternalMdl</a>
</dt>
<dt>
<a href="netvista.vmbpacketsendwithexternalpfns">VmbPacketSendWithExternalPfns</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbPacketSetCompletionRoutine function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

