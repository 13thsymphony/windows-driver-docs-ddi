---
UID: NF:portcls.IMiniportWavePciStream.GetPosition
title: IMiniportWavePciStream::GetPosition method
author: windows-driver-content
description: The GetPosition method gets the current position of the stream.
old-location: audio\iminiportwavepcistream_getposition.htm
old-project: audio
ms.assetid: 61575632-62f8-47d3-9249-5f5416191dfa
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportWavePciStream, IMiniportWavePciStream::GetPosition, GetPosition
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
req.alt-api: IMiniportWavePciStream.GetPosition
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
req.irql: PASSIVE_LEVEL
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IMiniportWavePciStream::GetPosition method



## -description
The <code>GetPosition</code> method gets the current position of the stream.



## -syntax

````
NTSTATUS GetPosition(
  [out] PULONGLONG Position
);
````


## -parameters

### -param Position [out]

Output pointer for the position value. This parameter points to a caller-allocated ULONGLONG variable into which the method writes the current byte position of the stream.


## -returns
<code>GetPosition</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks
The position indicated by the <code>GetPosition</code> method is expressed as a byte offset from the beginning of the stream. It represents the miniport driver's best estimate of the byte position of the data currently in the DAC or ADC. The miniport object is required to maintain stream position based on the mappings it acquires, regardless of whether mappings are released or revoked.

The position is zero immediately following initialization of the stream. A transition to the KSSTATE_STOP state (see <a href="..\ks\ne-ks-pksstate.md">KSSTATE</a>) resets the position to zero. When the stream is halted by a transition from KSSTATE_RUN to KSSTATE_PAUSE or KSSTATE_ACQUIRE, the position freezes. It unfreezes when the stream transitions from KSSTATE_PAUSE or KSSTATE_ACQUIRE back to KSSTATE_RUN.

The position reported by <code>GetPosition</code> is not an offset into any one physical buffer that either your driver has allocated or a client has allocated. Instead, the offset is stream-relative and can be thought of as an offset into an idealized buffer that contains the entire stream and is contiguous from beginning to end. Any internal offsets that point into the actual physical buffers that contain the data need to be maintained separately.

Note that the offset value retrieved by a <code>GetPosition</code> call is one of the following:

For a render stream, the <code>GetPosition</code> method retrieves the <i>play position</i>, which is the byte offset of the sample that is currently being played through the DAC and transmitted through the speaker jack.

For a capture stream, the <code>GetPosition</code> method retrieves the <i>record position</i>, which is the byte offset of the latest sample to be received through the microphone jack and captured by the ADC.

It is not the offset of the sample that the DMA engine in the audio device is currently reading from or writing to the audio buffer.

Some audio hardware contains a position register to keep track of the byte offset of the sample currently in each DAC or ADC, in which case the <code>GetPosition</code> method simply retrieves the contents of the position register for the appropriate stream. Other audio hardware can only supply the driver with DMA pointers into the audio buffers, in which case the <code>GetPosition</code> method must provide a best estimate of the byte offset in the DAC or ADC based on the current DMA position and the buffering delays internal to the device.

Audio hardware that internally buffers a portion of a playback or capture stream might make a precise position reading more difficult to obtain. In this case, the driver should estimate the current position as accurately as possible. For example, if an audio device prefetches the playback stream into an internal buffer, the driver might need to take both the buffer size and timing information into account in order to properly estimate the play position.

The WavePci port driver implements a property handler for <a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a>. This property handler calls the <code>GetPosition</code> method to obtain the current play or record position from the miniport driver. For more information, see <a href="https://msdn.microsoft.com/893fea84-9136-4107-96d2-8a4e2ab7bd2a">Audio Position Property</a>. 


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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iminiportwavepcistream.md">IMiniportWavePciStream</a>
</dt>
<dt>
<a href="..\ks\ne-ks-pksstate.md">KSSTATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWavePciStream::GetPosition method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

