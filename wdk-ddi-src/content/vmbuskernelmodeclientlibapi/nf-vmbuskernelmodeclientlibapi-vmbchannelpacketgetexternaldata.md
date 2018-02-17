---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelPacketGetExternalData
title: VmbChannelPacketGetExternalData function
author: windows-driver-content
description: The VmbChannelPacketGetExternalData function gets any external Memory Descriptor Lists (MDLs) associated with a packet during packet processing.
old-location: netvista\vmbchannelpacketgetexternaldata.htm
old-project: netvista
ms.assetid: 844AB898-E6F0-4C75-9364-1BE31AAB88E7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: VmbChannelPacketGetExternalData, netvista.vmbchannelpacketgetexternaldata, VmbChannelPacketGetExternalData function [Network Drivers Starting with Windows Vista], VMBUS_CHANNEL_PACKET_EXTERNAL_DATA_FLAG_READ_ONLY, vmbuskernelmodeclientlibapi/VmbChannelPacketGetExternalData
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
-	VmbChannelPacketGetExternalData
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbChannelPacketGetExternalData function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPacketGetExternalData</b>  function gets any external
Memory Descriptor Lists (MDLs) associated with a packet during packet processing.

## Syntax

````
NTSTATUS VmbChannelPacketGetExternalData(
  _In_  VMBPACKETCOMPLETION PacketCompletionContext,
  _In_  UINT32              Flags,
  _Out_ PMDL                *Mdl
);
````

## Parameters

`PacketCompletionContext`

A  handle that identifies the incoming packet and is used to refer to the packet
once processing is finished.

`Flags`

Flags that control how the MDL is mapped. The possible flag values are: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_PACKET_EXTERNAL_DATA_FLAG_READ_ONLY"></a><a id="vmbus_channel_packet_external_data_flag_read_only"></a><dl>
<dt><b>VMBUS_CHANNEL_PACKET_EXTERNAL_DATA_FLAG_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
Map MDL as read-only.

</td>
</tr>
</table>

`Mdl`

A pointer to the mapped MDL.


## Return Value

<b>VmbChannelPacketGetExternalData</b> returns a status code. If this function returns STATUS_PENDING,
the caller must return from the packet processing callback, which will be
called again, possibly at a different IRQL, when the external data is ready.
At this point, a call to this function will succeed and return the external
data.

## Remarks

Creating an MDL which represents the memory described by this
transaction causes these regions of the virtual machine to be pinned in memory for the remainder of the transaction lifetime.  This is what may cause the function to return STATUS_PENDING, because the regions of the
virtual machine may need to be paged in.


 The MDL returned by this function describes memory that is already
locked in place. Therefore, there is no need to call the
<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a> function.  The MDL will, however, have neither a user-mode virtual
address nor a kernel-mode virtual address.  If the driver that calls this function requires a virtual address to manipulate the memory within the virtual machine, that driver must call <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>,
and the corresponding unlock function later, like <a href="..\wdm\nf-wdm-mmunmaplockedpages.md">MmUnmapLockedPages</a>.
An alternative to using a virtual address would be to just pass the MDL on down to a driver which uses it for direct memory access. 

 The driver calling this function is not required to release the MDL.  It becomes invalid upon calling the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete.md">VmbChannelPacketComplete</a> function. The Kernel Mode Client Library (KMCL) later releases it.

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

<a href="..\wdm\nf-wdm-mmunmaplockedpages.md">MmUnmapLockedPages</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete.md">VmbChannelPacketComplete</a>



<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelPacketGetExternalData function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>