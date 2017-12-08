---
UID: NF.ks.KsStreamPointerGetNextClone
title: KsStreamPointerGetNextClone function
author: windows-driver-content
description: The KsStreamPointerGetNextClone function returns the clone stream pointer that was cloned immediately after the specified clone.
old-location: stream\ksstreampointergetnextclone.htm
old-project: stream
ms.assetid: b7f34d42-6044-43c6-85c8-ca3a6177c057
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsStreamPointerGetNextClone
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
req.alt-api: KsStreamPointerGetNextClone
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

# KsStreamPointerGetNextClone function



## -description
The<b> KsStreamPointerGetNextClone </b>function returns the clone stream pointer that was cloned immediately after the specified clone.


## -syntax

````
PKSSTREAM_POINTER KsStreamPointerGetNextClone(
  _In_ PKSSTREAM_POINTER StreamPointer
);
````


## -parameters

### -param StreamPointer [in]

A pointer to a <a href="stream.ksstream_pointer">KSSTREAM_POINTER</a> structure representing the clone stream pointer for which the clone stream pointer cloned immediately after it on the same pin is returned.

## -returns
<b>KsStreamPointerGetNextClone </b>returns a pointer to a <a href="stream.ksstream_pointer">KSSTREAM_POINTER</a> structure representing the clone stream pointer that was cloned immediately after <i>StreamPointer</i> on the same pin. Alternatively, it returns <b>NULL</b> indicating that either <i>StreamPointer</i> is the last clone on the pin or that <i>StreamPointer</i> is not a clone. If not a clone, <i>StreamPointer</i> is either the leading or trailing edge stream pointer.

## -remarks
The returned pointer always refers to the same pin as <i>StreamPointer</i>. <b>KsStreamPointerGetNextClone</b>, in conjunction with <a href="stream.kspingetfirstclonestreampointer">KsPinGetFirstCloneStreamPointer</a>,<b></b>can be used to enumerate all clone stream pointers on a given pin in the order in which they were cloned.

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
<a href="stream.kspingetfirstclonestreampointer">KsPinGetFirstCloneStreamPointer</a>
</dt>
<dt>
<a href="stream.ksstreampointerclone">KsStreamPointerClone</a>
</dt>
<dt>
<a href="stream.ksstreampointerdelete">KsStreamPointerDelete</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerGetNextClone function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
