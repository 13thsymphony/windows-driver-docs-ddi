---
UID: NC.ks.PFNKSSTREAMPOINTER
title: PFNKSSTREAMPOINTER
author: windows-driver-content
description: AVStream calls a minidriver's AVStrMiniCancelCallback routine when the IRP that is associated with a cloned stream pointer is canceled. This routine is optional.
old-location: stream\avstrminicancelcallback.htm
old-project: stream
ms.assetid: 4c95ccb6-c796-4bb2-b344-aa8eea28e131
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVStrMiniCancelCallback
req.alt-loc: ks.h
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

# PFNKSSTREAMPOINTER callback



## -description
AVStream calls a minidriver's <i>AVStrMiniCancelCallback</i> routine when the IRP that is associated with a cloned stream pointer is canceled. This routine is optional.



## -prototype

````
PFNKSSTREAMPOINTER AVStrMiniCancelCallback;

void AVStrMiniCancelCallback(
  _In_ PKSSTREAM_POINTER StreamPointer
)
{ ... }
````


## -parameters

### -param StreamPointer [in]

A pointer to the clone <a href="stream.ksstream_pointer">KSSTREAM_POINTER</a> that is associated with the IRP that was canceled. <i>StreamPointer</i> was created by a call to <a href="stream.ksstreampointerclone">KsStreamPointerClone</a>.


## -returns
None


## -remarks
The minidriver specifies this routine's address in the <i>CancelCallback</i> parameter of <a href="stream.ksstreampointerclone">KsStreamPointerClone</a>.

In <i>AVStrMiniCancelCallback</i>, the minidriver should set all references to the clone pointer to <b>NULL</b>.

In addition, the minidriver should remove any context information that is related to the clone pointer, and notify hardware about the cancellation.

Finally, the minidriver must call <a href="stream.ksstreampointerdelete">KsStreamPointerDelete</a> to delete the clone and the context associated with it. If the minidriver does not delete the clone, the IRP will retain a reference count and not complete, possibly causing related applications to crash.

<i>AVStrMiniCancelCallback</i> is called with the queue's spin lock held, hence at DISPATCH_LEVEL. Accordingly, the callback routine cannot perform queue manipulation or call functions that acquire a mutex.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksstreampointerclone">KsStreamPointerClone</a>
</dt>
<dt>
<a href="stream.ksstreampointerdelete">KsStreamPointerDelete</a>
</dt>
<dt>
<a href="stream.ksstream_pointer">KSSTREAM_POINTER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVStrMiniCancelCallback routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

