---
UID: NF.portcls.IPortWavePciStream.TerminatePacket
title: IPortWavePciStream::TerminatePacket method
author: windows-driver-content
description: The TerminatePacket method terminates the packet currently being mapped.
old-location: audio\iportwavepcistream_terminatepacket.htm
old-project: audio
ms.assetid: b85c37ff-b8f0-43df-bce2-f8a85ec050a7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortWavePciStream, IPortWavePciStream::TerminatePacket, TerminatePacket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortWavePciStream.TerminatePacket
req.alt-loc: portcls.h
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
---

# IPortWavePciStream::TerminatePacket method



## -description
The <code>TerminatePacket</code> method terminates the packet currently being mapped.



## -syntax

````
NTSTATUS TerminatePacket(
    None
);
````


## -parameters

### -param None 


## -returns
<code>TerminatePacket</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks
This method is used primarily for capture situations in which I/O packets need to end at specific points in the stream (for example, to synchronize with video frames). The data buffer for a capture pin on an audio device consists of one or more I/O packets. Each I/O packet is the portion of the data buffer that is attached to a particular mapping IRP. By default, while a capture stream is in the KSSTATE_RUN state, the contents of an I/O packet become available to the client only when the last mapping in the packet has been filled. The <code>TerminatePacket</code> method makes a partially filled packet immediately available to the client without waiting for additional capture data.

Changing the state of a capture stream from KSSTATE_RUN to KSSTATE_STOP automatically terminates the current I/O packet.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
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