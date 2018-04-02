---
UID: NF:portcls.IMiniportMidiStream.Read
title: IMiniportMidiStream::Read method
author: windows-driver-content
description: The Read method reads data from an incoming MIDI stream.
old-location: audio\iminiportmidistream_read.htm
old-project: audio
ms.assetid: 448dc408-c47f-4c8b-8baf-a831c69c3020
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMiniportMidiStream, IMiniportMidiStream interface [Audio Devices], Read method, IMiniportMidiStream::Read, Read method [Audio Devices], Read method [Audio Devices], IMiniportMidiStream interface, Read,IMiniportMidiStream.Read, audio.iminiportmidistream_read, audmp-routines_35ce63a1-ab31-4758-887a-9043e1f65915.xml, portcls/IMiniportMidiStream::Read
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportMidiStream.Read
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMiniportMidiStream::Read method
The <code>Read</code> method reads data from an incoming MIDI stream.

## Syntax

```
NTSTATUS Read(
  PVOID  BufferAddress,
  ULONG  BufferLength,
  PULONG BytesRead
);
```

## Parameters

`BufferAddress`

Specifies the address of a caller-allocated buffer. The method copies the incoming MIDI data from the device to the buffer. The allocated size of this buffer must be greater than or equal to <i>BufferLength</i>.

`BufferLength`

Specifies the length in bytes of the buffer pointed to by <i>BufferAddress</i>.

`BytesRead`

Output pointer to a caller-allocated variable into which the method writes a count specifying the actual number of bytes successfully read from the device into the buffer.


## Return Value

<code>Read</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Invalid device request (for example, calling <code>Read</code> on a MIDI output stream).

</td>
</tr>
</table>

## Remarks

The miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a> to notify the port driver when incoming MIDI data becomes available from the capture device. The port driver calls <b>IMiniportMidi::Read</b> to retrieve the data. The port driver continues to call <code>Read</code> as long as more data is available.

The <code>Read</code> method returns STATUS_SUCCESS and a <i>BytesRead</i> count of zero to indicate that no more MIDI input data is currently available from the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536704">IMiniportMidiStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536708">IMiniportMidiStream::Write</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a>