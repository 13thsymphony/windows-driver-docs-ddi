---
UID : NF:portcls.IMiniportMidiStream.Read
title : IMiniportMidiStream::Read method
author : windows-driver-content
description : The Read method reads data from an incoming MIDI stream.
old-location : audio\iminiportmidistream_read.htm
old-project : audio
ms.assetid : 448dc408-c47f-4c8b-8baf-a831c69c3020
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IMiniportMidiStream interface [Audio Devices], Read method, audmp-routines_35ce63a1-ab31-4758-887a-9043e1f65915.xml, IMiniportMidiStream, Read method [Audio Devices], IMiniportMidiStream interface, Read, Read method [Audio Devices], portcls/IMiniportMidiStream::Read, IMiniportMidiStream::Read, audio.iminiportmidistream_read
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : portcls.h
req.dll : 
req.irql : DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# Read method
The <code>Read</code> method reads data from an incoming MIDI stream.

## Syntax

````
NTSTATUS Read(
  [in]  PVOID  BufferAddress,
  [in]  ULONG  BufferLength,
  [out] PULONG BytesRead
);
````

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
| **Library** | portcls.h |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a>

<a href="..\portcls\nn-portcls-iminiportmidistream.md">IMiniportMidiStream</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536708">IMiniportMidiStream::Write</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportMidiStream::Read method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>