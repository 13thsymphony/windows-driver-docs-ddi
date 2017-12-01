---
UID: NF.vmbuskernelmodeclientlibapi.VmbPacketInitialize
title: VmbPacketInitialize
author: windows-driver-content
description: The VmbPacketInitialize function initializes a buffer to contain a VMBus packet.
old-location: netvista\vmbpacketinitialize.htm
old-project: netvista
ms.assetid: D5D8D994-0BB6-44FC-A696-F2E0264445C1
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: VmbPacketInitialize
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
req.alt-api: VmbPacketInitialize
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
req.iface: 
req.product: Windows 10 or later.
---

# VmbPacketInitialize function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <b>VmbPacketInitialize</b> function initializes a buffer to contain a VMBus packet. </p>


## -syntax

````
NTSTATUS
 VmbPacketInitialize(
  _In_  VMBCHANNEL                         Channel,
  _Out_ writes_bytes_(ByteCount) VMBPACKET VmbPacket,
  _In_  UINT32                             ByteCount
);
````


## -parameters
<dl>

### -param <i>Channel</i> [in]

<dd>
<p>A handle for a channel.
</p>
</dd>

### -param <i>VmbPacket</i> [out]

<dd>
<p>The buffer to use to store the VMBus packet.
</p>
</dd>

### -param <i>ByteCount</i> [in]

<dd>
<p>The size of <i>Buffer</i>, in bytes.</p>
</dd>
</dl>

## -returns
<p><b>VmbPacketInitialize</b> returns the following status codes:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p> The function finished successfully.
</p><dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl><p>The value of  <i>ByteCount</i> is not valid. It needs to be greater than the maximum packet size plus the size of a void pointer. </p>

<p> </p>

## -remarks
<p>The size of the buffer must be at
least the size calculated by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsizeofpacket.md">VmbChannelSizeofPacket</a> function.  </p>

<p><b>VmbPacketInitialize</b> is  an alternative
to the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketallocate.md">VmbPacketAllocate</a> function. Use the current function if the caller supplies the
memory for the packet object. </p>

<p>The packet's initial completion routine is invalid and must be set before
sending the packet.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.13</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
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
<p>Library</p>
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
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsizeofpacket.md">VmbChannelSizeofPacket</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketallocate.md">VmbPacketAllocate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbPacketInitialize function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
