---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSendSynchronousRequest
title: VmbChannelSendSynchronousRequest function
author: windows-driver-content
description: The VmbChannelSendSynchronousRequest function sends a packet to the opposite endpoint and waits for a response.
old-location: netvista\vmbchannelsendsynchronousrequest.htm
old-project: netvista
ms.assetid: 312DED8E-570E-4DEC-B084-36894970F49F
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: vmbuskernelmodeclientlibapi/VmbChannelSendSynchronousRequest, netvista.vmbchannelsendsynchronousrequest, VmbChannelSendSynchronousRequest, VmbChannelSendSynchronousRequest function [Network Drivers Starting with Windows Vista]
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
-	VmbChannelSendSynchronousRequest
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product: Windows 10 or later.
---


# VmbChannelSendSynchronousRequest function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSendSynchronousRequest</b> function sends a packet to the opposite endpoint and waits for a response.

## Syntax

````
NTSTATUS VmbChannelSendSynchronousRequest(
  _In_        VMBCHANNEL                                                               Channel,
  _In_        reads_bytes_(BufferSize)   PVOID                                         Buffer,
  _In_        UINT32                                                                   BufferSize,
  _In_opt_    PMDL                                                                     ExternalDataMdl,
  _In_        UINT32                                                                   Flags,
  _Out_       writes_bytes_to_opt_(*CompletionBufferSize, *CompletionBufferSize) PVOID CompletionBuffer,
  _Inout_opt_ _Pre_satisfies_(*_Curr_ % 8 == 0) PUINT32                                CompletionBufferSize,
  _In_opt_    PLARGE_INTEGER                                                           Timeout
);
````

## Parameters

`Channel`

A handle for the channel.

`Buffer`

Data to send.

`BufferSize`

The size, in bytes, of the data to send.

`ExternalDataMdl`

A Memory Descriptor List (MDL) that describes an additional buffer to     send.

`Flags`

Standard flags.

`CompletionBuffer`

Buffer in which to store completion packet results.

`CompletionBufferSize`

The size, in bytes, of the <i>CompletionBuffer</i> value. This value must be     rounded up to nearest 8 bytes, or else the function fails. On success,
returns the number of bytes written into <i>CompletionBuffer</i>.

`Timeout`

A timeout in the style of the <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a> routing.
After this time elapses, the packet is cancelled. For a timeout of zero (0), if a packet does not fir in the ring buffer, it is not queued.


## Return Value

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
The functions finished successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The packet did not fit in the buffer and
was not queued.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The packet was canceled.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The channel is being shut down.

</td>
</tr>
</table>

## Remarks

Clients can run this function with any combination of parameters. 

The root may only call
this if <code>*Timeout == 0</code> and the <b>VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION</b> flag is not set.

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

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelSendSynchronousRequest function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>