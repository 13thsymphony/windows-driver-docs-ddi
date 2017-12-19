---
UID: NF.ks.KsPinGetAvailableByteCount
title: KsPinGetAvailableByteCount function
author: windows-driver-content
description: The KsPinGetAvailableByteCount routine outputs the number of bytes of input data ahead of the leading edge and the number of bytes of output buffer ahead of the leading edge, both for the queue of a caller-specified pin.
old-location: stream\kspingetavailablebytecount.htm
old-project: stream
ms.assetid: e3669f11-7284-4f65-b814-624337e7fa7f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsPinGetAvailableByteCount
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
req.alt-api: KsPinGetAvailableByteCount
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
req.irql: 
---

# KsPinGetAvailableByteCount function



## -description
The<b> KsPinGetAvailableByteCount</b> routine outputs the number of bytes of input data ahead of the leading edge and the number of bytes of output buffer ahead of the leading edge, both for the queue of a caller-specified pin.



## -syntax

````
NTSTATUS KsPinGetAvailableByteCount(
  _In_      PKSPIN Pin,
  _Out_opt_ PLONG  InputDataBytes,
  _Out_opt_ PLONG  OutputBufferBytes
);
````


## -parameters

### -param Pin [in]

A pointer to a <a href="stream.kspin">KSPIN</a> structure for which to calculate these queue parameters.


### -param InputDataBytes [out, optional]

A pointer to a LONG value in which the routine returns the number of input data bytes ahead of the leading edge. Caller sets to <b>NULL</b> if this value is not requested.


### -param OutputBufferBytes [out, optional]

A pointer to  a LONG value in which the routine returns the number of output buffer bytes ahead of the leading edge. Caller sets to <b>NULL</b> if this value is not requested.


## -returns
Returns STATUS_SUCCESS if the requested count(s) have been retrieved. A nonsuccessful return status indicates that <i>Pin</i> does not have an associated queue.


## -remarks
Noninplace pins should use <i>InputDataBytes</i> for input pins and <i>OutputBufferBytes</i> for output pins.

The results of this call are not guaranteed to be safe unless either the processing mutex is held at call-time, or the caller has privately synchronized before calling the routine. To private synchronize, ensure that the pin does not transition from Acquire to Stop while the routine is executing. See <a href="https://msdn.microsoft.com/dd84fe3f-352e-4641-99d7-792ccecb0b40">Processing Mutex in AVStream</a>.

Also note that in-place transform can supply input and output counts.

In Windows XP and DirectX 8.0, the <i>InputDataBytes</i> count is not valid unless frames that the filter receives are full.

For additional information, see <a href="https://msdn.microsoft.com/73ab974f-8034-421f-980a-2393d84ec54c">Leading and Trailing Edge Stream Pointers</a>.


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
</table>

## -see-also
<dl>
<dt>
<a href="stream.kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>
</dt>
<dt>
<a href="stream.kspingetleadingedgestreampointer">KsPinGetLeadingEdgeStreamPointer</a>
</dt>
<dt>
<a href="stream.kspingettrailingedgestreampointer">KsPinGetTrailingEdgeStreamPointer</a>
</dt>
<dt>
<a href="stream.ksstream_pointer">KSSTREAM_POINTER</a>
</dt>
<dt>
<a href="stream.kspin_dispatch">KSPIN_DISPATCH</a>
</dt>
<dt>
<a href="stream.avstrminipinprocess">AVStrMiniPinProcess</a>
</dt>
<dt>
<a href="stream.ksfilteracquireprocessingmutex">KsFilterAcquireProcessingMutex</a>
</dt>
<dt>
<a href="stream.kspinacquireprocessingmutex">KsPinAcquireProcessingMutex</a>
</dt>
<dt>
<a href="stream.ksfilterreleaseprocessingmutex">KsFilterReleaseProcessingMutex</a>
</dt>
<dt>
<a href="stream.kspinreleaseprocessingmutex">KsPinReleaseProcessingMutex</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetAvailableByteCount routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

