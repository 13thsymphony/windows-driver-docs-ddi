---
UID: NF:portcls.IMiniportMidiStream.Write
title: IMiniportMidiStream::Write method
author: windows-driver-content
description: The Write method writes data to an outgoing MIDI stream.
old-location: audio\iminiportmidistream_write.htm
old-project: audio
ms.assetid: 6ff4e4d7-3ba4-4e4b-98fa-62f269aee69f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportMidiStream, IMiniportMidiStream::Write, Write
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
req.alt-api: IMiniportMidiStream.Write
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
req.irql: DISPATCH_LEVEL
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IMiniportMidiStream::Write method



## -description
The <code>Write</code> method writes data to an outgoing MIDI stream.



## -syntax

````
NTSTATUS Write(
  [in]  PVOID  BufferAddress,
  [in]  ULONG  BytesToWrite,
  [out] PULONG BytesWritten
);
````


## -parameters

### -param BufferAddress [in]

Pointer to a caller-allocated buffer that contains the outgoing MIDI data


### -param BytesToWrite [in]

Specifies the number of bytes of MIDI data contained in the buffer that <i>BufferAddress</i> points to.


### -param BytesWritten [out]

Output pointer to a caller-allocated variable into which the method writes a count specifying the actual number of bytes that the method succeeded in writing to the MIDI output device. For more information, see the following Remarks section.


## -returns
<code>Write</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.
<dl>
<dt><b>STATUS_IO_DEVICE_ERROR</b></dt>
</dl>The call failed due to a device error.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>Invalid device request (for example, calling <code>Write</code> on a MIDI input stream).

 


## -remarks
If the method succeeds, it outputs one of the following values to the caller through the <i>BytesWritten</i> parameter:

The same value as <i>BytesToWrite</i>. This value indicates that the method succeeded in writing all <i>BytesToWrite</i> bytes of data to the device.

A multiple of four that is less than <i>BytesToWrite</i>. If the method is able to write some but not all of the caller's data to the device, it should write a number of bytes that is a multiple of four. This value indicates that the caller should make another call to the method to write the remaining data.

Zero. This value indicates that the device is too busy to write any of the caller's data during the current call, but that the caller should try again later. The miniport driver is responsible for distinguishing a busy device from a device error. The method should avoid generating an endless succession of calls that always return success but write zero bytes.


## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iminiportmidistream.md">IMiniportMidiStream</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536705">IMiniportMidiStream::Read</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportMidiStream::Write method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

