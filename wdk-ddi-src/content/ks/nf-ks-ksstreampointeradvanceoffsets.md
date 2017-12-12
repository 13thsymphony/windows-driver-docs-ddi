---
UID: NF.ks.KsStreamPointerAdvanceOffsets
title: KsStreamPointerAdvanceOffsets function
author: windows-driver-content
description: The KsStreamPointerAdvanceOffsets function advances the offsets of StreamPointer.
old-location: stream\ksstreampointeradvanceoffsets.htm
old-project: stream
ms.assetid: 0377371b-b755-4473-a449-9a85e1ca456c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsStreamPointerAdvanceOffsets
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsStreamPointerAdvanceOffsets
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# KsStreamPointerAdvanceOffsets function



## -description
The<b> KsStreamPointerAdvanceOffsets</b> function advances the offsets of <i>StreamPointer</i>.



## -syntax

````
NTSTATUS KsStreamPointerAdvanceOffsets(
  _In_ PKSSTREAM_POINTER StreamPointer,
  _In_ ULONG             InUsed,
  _In_ ULONG             OutUsed,
  _In_ BOOLEAN           Eject
);
````


## -parameters

### -param StreamPointer [in]

A pointer to a <a href="stream.ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer for which to advance the offsets. <i>StreamPointer</i> should be in the locked state when this function is called.


### -param InUsed [in]

The number of bytes to advance the input pointer of this stream pointer. 

(StreamPointer -&gt; OffsetIn)


### -param OutUsed [in]

The number of bytes to advance the output pointer of this stream pointer 

(StreamPointer -&gt; OffsetOut)


### -param Eject [in]

This parameter indicates whether the stream pointer should be advanced to the next data frame If this parameter is set to <b>TRUE</b>, AVStream advances the stream pointer regardless of whether advancing the offsets causes the stream pointer to point to the end of a frame.


## -returns
<b>KsStreamPointerAdvanceOffsets</b> returns STATUS_SUCCESS on success. Returns STATUS_DEVICE_NOT_READY if either <i>StreamPointer</i> was not locked at call-time or that the stream pointer could not be locked after advancement.


## -remarks
AVStream updates the in and out data pointers and other related fields by the requested values. If advancing the offsets results in zero bytes remaining in the current frame, AVStream advances the stream pointer to the next data frame and relocks it.

It is the responsibility of the minidriver to verify that <i>StreamPointer</i> is locked before calling <b>KsStreamPointerAdvanceOffsets</b>. Also, a single advancement cannot advance a stream pointer further than the beginning of the next frame in the queue. Thus, minidrivers should not attempt to advance offsets by a value greater than <i>StreamPointer -&gt; Offset*.Remaining</i>. 

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>. 


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
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
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

## -see-also
<dl>
<dt>
<a href="stream.ksstreampointerlock">KsStreamPointerLock</a>
</dt>
<dt>
<a href="stream.ksstreampointerunlock">KsStreamPointerUnlock</a>
</dt>
<dt>
<a href="stream.ksstreampointeradvance">KsStreamPointerAdvance</a>
</dt>
<dt>
<a href="stream.ksstreampointeradvanceoffsetsandunlock">KsStreamPointerAdvanceOffsetsAndUnlock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerAdvanceOffsets function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

