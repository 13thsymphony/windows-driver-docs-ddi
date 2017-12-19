---
UID: NC.vmbuskernelmodeclientlibapi.EVT_VMB_PACKET_COMPLETION_ROUTINE
title: EVT_VMB_PACKET_COMPLETION_ROUTINE
author: windows-driver-content
description: The EvtVmbPacketCompletionRoutine callback function is invoked when the transaction associated with a sent packet is complete.
old-location: netvista\evt_vmb_packet_completion_routine.htm
old-project: NetVista
ms.assetid: DEE6FBD6-4807-4216-9010-F59C9E08076B
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _VIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES, PVIDEO_PORT_AGP_SERVICES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_VMB_PACKET_COMPLETION_ROUTINE
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
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# EVT_VMB_PACKET_COMPLETION_ROUTINE callback



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbPacketCompletionRoutine</i> callback function is invoked when the transaction associated with a sent packet
is complete.  



## -prototype

````
EVT_VMB_PACKET_COMPLETION_ROUTINE EvtVmbPacketCompletionRoutine;

VOID EvtVmbPacketCompletionRoutine(
  _In_ VMBPACKET                            Packet,
  _In_ NTSTATUS                             Status,
  _In_ reads_bytes_opt_(BufferLength) PVOID Buffer,
  _In_ UINT32                               BufferLength
)
{ ... }

typedef EVT_VMB_PACKET_COMPLETION_ROUTINE PFN_VMB_PACKET_COMPLETION_ROUTINE;
````


## -parameters

### -param Packet [in]

The packet that is completed.



### -param Status [in]

A status code.


### -param Buffer [in]

A buffer that contains the completion response from the opposite endpoint, if any.



### -param BufferLength [in]

Length of the <i>Buffer</i> parameter, in bytes.


## -returns
This callback function does not return a value.


## -remarks
After allocating a packet object by using the <a href="netvista.vmbpacketallocate">VmbPacketAllocate</a> function, the client drive can set a completion callback by using the <a href="netvista.vmbpacketsetcompletionroutine">VmbPacketSetCompletionRoutine</a> function.  

If the sender used the VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION
flag, invocation of this callback means that the opposite endpoint received the packet and completed it.
If not, the outgoing packet was successfully placed into the ring buffer.


## -requirements
<table>
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
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.vmbpacketallocate">VmbPacketAllocate</a>
</dt>
<dt>
<a href="netvista.vmbpacketsetcompletionroutine">VmbPacketSetCompletionRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20EVT_VMB_PACKET_COMPLETION_ROUTINE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

