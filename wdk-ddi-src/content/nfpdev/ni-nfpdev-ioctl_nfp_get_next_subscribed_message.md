---
UID: NI.nfpdev.IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE
title: IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE
author: windows-driver-content
description: The client sends the IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE request to the subscription handle repeatedly in order to receive subscribed messages as they arrive.
old-location: nfpdrivers\ioctl_nfp_get_next_subscribed_message.htm
old-project: nfpdrivers
ms.assetid: 975C32AE-6A2C-44C8-8F53-4158FDF1B942
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _SECURE_ELEMENT_TECH_ROUTING_INFO, *PSECURE_ELEMENT_TECH_ROUTING_INFO, SECURE_ELEMENT_TECH_ROUTING_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfpdev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE
req.alt-loc: nfpdev.h
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
---

# IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE IOCTL



## -description
The client sends the <b>IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE</b> request to the subscription handle repeatedly in order to receive subscribed messages as they arrive.  Typically, this IOCTL will be pended in the subscription handle until a message matching the subscribed type actually arrives.



## -ioctlparameters

### -input-buffer
None


### -input-buffer-length

<text></text>

### -output-buffer
A valid buffer is required for returning the message data when it arrives.  The first <b>DWORD</b> of this buffer is reserved for a hint to the client for the next size of the buffer to be returned.  This buffer will typically initially be 255 bytes, but the driver can request that the client send a bigger buffer by providing just the hint and completing the IOCTL with STATUS_BUFFER_OVERFLOW.


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks
The client should send another IOCTL each time the pended one is completed. The driver MUST use appropriate locks to guarantee that the number of successful completions of this IOCTL equates to the number of successful message receptions for the subscription type.

The following are required actions when using this IOCTL:<ul>
<li>
If this IOCTL is received on a handle that wasn’t previously opened in the “Subs\” device namespace, the driver MUST complete it with STATUS_INVALID_DEVICE_STATE.

</li>
<li>
The driver must maintain a “Received” queue of received messages that match the subscription type within the subscription file handle.

</li>
<li>
	When this IOCTL is received in the driver:

<ul>
<li>
If the “Received” queue is empty, then the driver MUST pend the IOCTL for later completion.

</li>
<li>
	If the “Received” queue is non-empty, then the driver MUST dequeue one message buffer, copy the message buffer to the IOCTL’s output buffer, and complete the IOCTL with STATUS_SUCCESS immediately.

</li>
</ul>
</li>
<li>
If a message matching the type is received and no IOCTL is currently pended, the driver MUST add the message buffer to the “Received” queue.

</li>
<li>
	If a message matching the type is received and there is a pended IOCTL available (the “Received” queue is empty), the driver MUST copy the message buffer to the IOCTL’s output buffer and complete the pended IRP with STATUS_SUCCESS. The “Received” queue MUST continue to be empty following completion of the pended IRP.

</li>
<li>
	If the driver completes this IOCTL with STATUS_SUCCESS, the first DWORD [4 bytes] of the output buffer MUST contain a hint for the size of the next client buffer and the IOCTL’s Information field MUST contain the size of this message plus <b>sizeof</b>(DWORD) (4 bytes).

</li>
<li>
	If the IOCTL contains an input buffer the driver MUST complete the IOCTL with STATUS_INVALID_PARAMETER.

</li>
<li>
	If a received message has a zero-length payload the driver SHOULD ignore the message.  This is a performance optimization because Windows WILL drop messages with zero-length payloads.

</li>
<li>
If a received message is too large to be copied into this IOCTL’s buffer, the driver MUST copy the required buffer size into the first 4 bytes of the output buffer, set the IOCTL’s “Information” field to sizeof(DWORD) (“4”), and complete the IOCTL with STATUS_BUFFER_OVERFLOW. The message buffer must be left in the “Received” queue.

</li>
<li>
If this IOCTL is received while another is currently pended in the subscription handle, the second (or later) one MUST be completed with STATUS_INVALID_DEVICE_STATE.

</li>
<li>
The driver MUST support CancelIo of the pended IOCTL.

</li>
</ul>


If this IOCTL is received on a handle that wasn’t previously opened in the “Subs\” device namespace, the driver MUST complete it with STATUS_INVALID_DEVICE_STATE.

The driver must maintain a “Received” queue of received messages that match the subscription type within the subscription file handle.

	When this IOCTL is received in the driver:

If the “Received” queue is empty, then the driver MUST pend the IOCTL for later completion.

	If the “Received” queue is non-empty, then the driver MUST dequeue one message buffer, copy the message buffer to the IOCTL’s output buffer, and complete the IOCTL with STATUS_SUCCESS immediately.

If a message matching the type is received and no IOCTL is currently pended, the driver MUST add the message buffer to the “Received” queue.

	If a message matching the type is received and there is a pended IOCTL available (the “Received” queue is empty), the driver MUST copy the message buffer to the IOCTL’s output buffer and complete the pended IRP with STATUS_SUCCESS. The “Received” queue MUST continue to be empty following completion of the pended IRP.

	If the driver completes this IOCTL with STATUS_SUCCESS, the first DWORD [4 bytes] of the output buffer MUST contain a hint for the size of the next client buffer and the IOCTL’s Information field MUST contain the size of this message plus <b>sizeof</b>(DWORD) (4 bytes).

	If the IOCTL contains an input buffer the driver MUST complete the IOCTL with STATUS_INVALID_PARAMETER.

	If a received message has a zero-length payload the driver SHOULD ignore the message.  This is a performance optimization because Windows WILL drop messages with zero-length payloads.

If a received message is too large to be copied into this IOCTL’s buffer, the driver MUST copy the required buffer size into the first 4 bytes of the output buffer, set the IOCTL’s “Information” field to sizeof(DWORD) (“4”), and complete the IOCTL with STATUS_BUFFER_OVERFLOW. The message buffer must be left in the “Received” queue.

If this IOCTL is received while another is currently pended in the subscription handle, the second (or later) one MUST be completed with STATUS_INVALID_DEVICE_STATE.

The driver MUST support CancelIo of the pended IOCTL.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Nfpdev.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) overall design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfp-design-guide">Near field proximity design guide (Tap and Do, NFP provider model, driver requirements)</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE control code%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

