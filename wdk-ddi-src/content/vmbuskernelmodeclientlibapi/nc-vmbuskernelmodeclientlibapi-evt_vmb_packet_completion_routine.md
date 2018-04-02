---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_PACKET_COMPLETION_ROUTINE
title: EVT_VMB_PACKET_COMPLETION_ROUTINE
author: windows-driver-content
description: The EvtVmbPacketCompletionRoutine callback function is invoked when the transaction associated with a sent packet is complete.
old-location: netvista\evt_vmb_packet_completion_routine.htm
old-project: netvista
ms.assetid: DEE6FBD6-4807-4216-9010-F59C9E08076B
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EVT_VMB_PACKET_COMPLETION_ROUTINE, EvtVmbPacketCompletionRoutine, EvtVmbPacketCompletionRoutine callback function [Network Drivers Starting with Windows Vista], PFN_VMB_PACKET_COMPLETION_ROUTINE, PFN_VMB_PACKET_COMPLETION_ROUTINE callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_packet_completion_routine, vmbuskernelmodeclientlibapi/EvtVmbPacketCompletionRoutine
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	PFN_VMB_PACKET_COMPLETION_ROUTINE
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# EVT_VMB_PACKET_COMPLETION_ROUTINE callback function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbPacketCompletionRoutine</i> callback function is invoked when the transaction associated with a sent packet
is complete.

## Syntax

```
EVT_VMB_PACKET_COMPLETION_ROUTINE EvtVmbPacketCompletionRoutine;

void EvtVmbPacketCompletionRoutine(
  VMBPACKET Packet,
  NTSTATUS Status,
  PVOID Buffer,
  UINT32 BufferLength
)
{...}
```

## Parameters

`Packet`

The packet that is completed.

`Status`

A status code.

`Buffer`

A buffer that contains the completion response from the opposite endpoint, if any.

`BufferLength`

Length of the <i>Buffer</i> parameter, in bytes.


## Return Value

This callback function does not return a value.

## Remarks

After allocating a packet object by using the <a href="https://msdn.microsoft.com/F121A7BC-5504-4CF5-8C8A-0568D6C4F77F">VmbPacketAllocate</a> function, the client drive can set a completion callback by using the <a href="https://msdn.microsoft.com/5781FE16-6CC8-425B-B14D-C78901D81A75">VmbPacketSetCompletionRoutine</a> function.  

If the sender used the VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION
flag, invocation of this callback means that the opposite endpoint received the packet and completed it.
If not, the outgoing packet was successfully placed into the ring buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/F121A7BC-5504-4CF5-8C8A-0568D6C4F77F">VmbPacketAllocate</a>



<a href="https://msdn.microsoft.com/5781FE16-6CC8-425B-B14D-C78901D81A75">VmbPacketSetCompletionRoutine</a>