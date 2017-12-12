---
UID: NF.vmbuskernelmodeclientlibapi.VmbPacketSendWithExternalPfns
title: VmbPacketSendWithExternalPfns function
author: windows-driver-content
description: The VmbPacketSendWithExternalPfns function sends the data in a packet buffer or external data as an array of Page Frame Numbers (PFNs).
old-location: netvista\vmbpacketsendwithexternalpfns.htm
old-project: netvista
ms.assetid: 50AACCAB-EFEA-42B7-8A34-FE110C7CDEED
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: VmbPacketSendWithExternalPfns
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
req.alt-api: VmbPacketSendWithExternalPfns
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
req.product: Windows 10 or later.
---

# VmbPacketSendWithExternalPfns function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSendWithExternalPfns</b> function sends the data in a packet buffer or external data as an array of Page Frame Numbers (PFNs). The function associates that data with the VMBus packet object, which represents the packet
throughout the lifetime of the transaction. 



## -syntax

````
NTSTATUS VmbPacketSendWithExternalPfns(
  _In_ __drv_aliasesMem VMBPACKET       PacketObject,
  _In_ reads_bytes_(BufferLength) PVOID Buffer,
  _In_ UINT32                           BufferLength,
  _In_ PPFN_NUMBER                      ExternalDataPfns,
  _In_ UINT32                           PfnOffset,
  _In_ UINT32                           PfnLength,
  _In_ UINT32                           Flags
);
````


## -parameters

### -param PacketObject [in]

A handle to the VMBus packet object.


### -param Buffer [in]

A buffer that contains the command packet that is sent
through the VMBus ring buffer.



### -param BufferLength [in]

The length, in bytes, of the buffer in the <i>Buffer</i> parameter. 


### -param ExternalDataPfns [in]

An array of Page Frame 
Numbers that describe a data buffer associated with 
the packet.


### -param PfnOffset [in]

The array index in the <i>ExternalDataPfns</i> value where 
the data starts.


### -param PfnLength [in]

The number of PFNs to send from 
<i>ExternalDataPfns</i>. The final referenced array index is  ExternalDataPfns[PfnOffset+PfnLength-1] inclusive.


### -param Flags [in]

Flags. The following are pertinent flags:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION

</td>
<td width="60%">
This packet cannot be considered complete and its resources cannot be released until a
completion packet comes back from the opposite endpoint. This flag must be set.

</td>
</tr>
<tr>

### -param VMBUS_CHANNEL_FORMAT_FLAG_PAGED_BUFFER

</td>
<td width="60%">
 The inline buffer is
paged and must be treated accordingly, which means it must be copied before entering DPC level.
Probing user-mode buffers or handling access violations is the
responsibility of the caller.

</td>
</tr>
</table>
 


## -returns
<b>VmbPacketSendWithExternalPfns</b> returns a status code.


## -remarks
This function differs from the <a href="netvista.vmbpacketsend">VmbPacketSend</a> function in that it allows passing an array of PFNs,  effectively physical addresses. 


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
</table>

## -see-also
<dl>
<dt>
<a href="netvista.vmbpacketsend">VmbPacketSend</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbPacketSendWithExternalPfns function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

