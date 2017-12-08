---
UID: NC.vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_RESTORE_PACKET
title: EVT_VMB_CHANNEL_RESTORE_PACKET
author: windows-driver-content
description: The EvtVmbChannelRestorePacket callback function is invoked when the virtualization service provider (VSP) server endpoint must restore the state associated with a packet object.
old-location: netvista\evt_vmb_channel_restore_packet.htm
old-project: netvista
ms.assetid: 9C89CFCB-4B8A-40D3-B982-2F7836A636A3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: VideoPortGetAgpServices
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
req.alt-api: PFN_VMB_CHANNEL_RESTORE_PACKET
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
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_RESTORE_PACKET callback



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <i>EvtVmbChannelRestorePacket</i> callback function is invoked when the virtualization service provider (VSP) server
endpoint must restore the state associated with a packet object.  </p>


## -prototype

````
EVT_VMB_CHANNEL_RESTORE_PACKET EvtVmbChannelRestorePacket;

NTSTATUS EvtVmbChannelRestorePacket(
  _In_ VMBCHANNEL                      Channel,
  _In_ reads_bytes_(LibBufSize) PVOID  LibBuf,
  _In_ UINT32                          LibBufSize,
  _In_ reads_bytes_(SaveBufSize) PVOID SaveBuf,
  _In_ UINT32                          SaveBufSize
)
{ ... }

typedef EVT_VMB_CHANNEL_RESTORE_PACKET PFN_VMB_CHANNEL_RESTORE_PACKET;
````


## -parameters
<dl>

### -param Channel [in]

<dd>
<p>The channel on which the packet arrives.</p>
</dd>

### -param LibBuf [in]

<dd>
<p>Pointer to packet object state internal to the Kernel Mode Client Library (KMCL).
</p>
</dd>

### -param LibBufSize [in]

<dd>
<p>Size of the <i>LibBuf</i> parameter, in bytes.
</p>
</dd>

### -param SaveBuf [in]

<dd>
<p>Pointer to transaction state specific to the VSP.
</p>
</dd>

### -param SaveBufSize [in]

<dd>
<p>Size of the <i>SaveBuf</i> parameter, in bytes.
</p>
</dd>
</dl>

## -returns
<p><i>EvtVmbChannelRestorePacket</i> returns a status code.</p>

## -remarks
<p>The <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetsaverestorepacketcallbacks.md">VmbServerChannelInitSetSaveRestorePacketCallbacks</a> function sets a callback function for restoring packets for each channel.</p>

<p>In order
to restore an in-flight packet object, the VSP must allocate a new packet
by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketallocate.md">VmbPacketAllocate</a> function. The VSP restores the packet to the previous state by passing <i>LibBuf</i> and <i>LibBufSize</i> to the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketrestore.md">VmbPacketRestore</a> function.
If the VSP provided any internal state for the transaction in the <i>EvtVmbChannelSavePacket</i>
callback function, then this is provided in <i>SaveBuf</i>, and restored by the VSP.</p>

## -requirements
<table>
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
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketallocate.md">VmbPacketAllocate</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketrestore.md">VmbPacketRestore</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetsaverestorepacketcallbacks.md">VmbServerChannelInitSetSaveRestorePacketCallbacks</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt-vmb-channel-restore-packet.md">EvtVmbChannelSavePacket</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_RESTORE_PACKET callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
