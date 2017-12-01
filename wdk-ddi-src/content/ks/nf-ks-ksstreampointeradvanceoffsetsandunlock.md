---
UID: NF.ks.KsStreamPointerAdvanceOffsetsAndUnlock
title: KsStreamPointerAdvanceOffsetsAndUnlock
author: windows-driver-content
description: The KsStreamPointerAdvanceOffsetsAndUnlock function advances StreamPointer the specified number of bytes into the stream (adjusting the OffsetIn and OffsetOut fields of StreamPointer as requested) and unlocks it.
old-location: stream\ksstreampointeradvanceoffsetsandunlock.htm
old-project: stream
ms.assetid: bb15eb8e-b609-4110-b0de-71efb8ef1f5e
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KsStreamPointerAdvanceOffsetsAndUnlock
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
req.alt-api: KsStreamPointerAdvanceOffsetsAndUnlock
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
req.iface: 
---

# KsStreamPointerAdvanceOffsetsAndUnlock function



## -description
<p>The<b> KsStreamPointerAdvanceOffsetsAndUnlock</b> function advances <i>StreamPointer</i> the specified number of bytes into the stream (adjusting the <i>OffsetIn </i>and <i>OffsetOut </i>fields of <i>StreamPointer</i> as requested) and unlocks it.</p>


## -syntax

````
void KsStreamPointerAdvanceOffsetsAndUnlock(
  _In_ PKSSTREAM_POINTER StreamPointer,
  _In_ ULONG             InUsed,
  _In_ ULONG             OutUsed,
  _In_ BOOLEAN           Eject
);
````


## -parameters
<dl>

### -param <i>StreamPointer</i> [in]

<dd>
<p>A pointer to a <a href="..\ks\ns-ks--ksstream-pointer.md">KSSTREAM_POINTER</a> structure representing the stream pointer to advance and unlock.</p>
</dd>

### -param <i>InUsed</i> [in]

<dd>
<p>This parameter contains the number of input bytes used. AVStream advances the input offset by this number of bytes. This must be less than the total number of remaining unused bytes in the frame referenced by <i>StreamPointer</i>. If <i>InUsed</i> is equal to the remaining number of bytes in the frame referenced by <i>StreamPointer</i>, AVStream advances <i>StreamPointer </i>to the next available data frame.</p>
</dd>

### -param <i>OutUsed</i> [in]

<dd>
<p>This parameter contains the number of output bytes used. AVStream advances the output offset by this number of bytes. This must be less than the total number of remaining unused bytes in the frame referenced by <i>StreamPointer</i>. If <i>OutUsed</i> is equal to the remaining number of bytes in the frame referenced by <i>StreamPointer</i>, AVStream advances <i>StreamPointer </i>to the next available data frame.</p>
</dd>

### -param <i>Eject</i> [in]

<dd>
<p>This parameter indicates whether <i>StreamPointer</i> should be advanced. If this parameter is set to <b>TRUE</b>, AVStream advances the stream pointer to the next available data frame regardless of the values in <i>InUsed </i>and <i>OutUsed</i>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If using the specified number of bytes in the stream pointer results in zero remaining bytes to process in the current frame, AVStream advances the stream pointer to the next available frame. Minidrivers can force advancement to the next frame regardless of the number of bytes used by setting <i>Eject</i>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksstreampointeradvance.md">KsStreamPointerAdvance</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksstreampointerunlock.md">KsStreamPointerUnlock</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksstreampointerlock.md">KsStreamPointerLock</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksstreampointerclone.md">KsStreamPointerClone</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksstreampointerdelete.md">KsStreamPointerDelete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerAdvanceOffsetsAndUnlock function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
