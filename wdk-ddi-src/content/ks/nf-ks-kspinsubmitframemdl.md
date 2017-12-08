---
UID: NF.ks.KsPinSubmitFrameMdl
title: KsPinSubmitFrameMdl function
author: windows-driver-content
description: If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrameMdl function submits a frame directly into the transport circuit.
old-location: stream\kspinsubmitframemdl.htm
old-project: stream
ms.assetid: 8033c0a9-86dd-4d54-b93e-66c926cae952
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsPinSubmitFrameMdl
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
req.alt-api: KsPinSubmitFrameMdl
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

# KsPinSubmitFrameMdl function



## -description
If a pin has been placed into injection mode by a call to <a href="stream.kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>, the <b>KsPinSubmitFrameMdl</b> function submits a frame directly into the transport circuit.


## -syntax

````
NTSTATUS KsPinSubmitFrameMdl(
  _In_     PKSPIN           Pin,
  _In_opt_ PMDL             Mdl,
  _In_opt_ PKSSTREAM_HEADER StreamHeader,
  _In_opt_ PVOID            Context
);
````


## -parameters

### -param Pin [in]

A pointer to a <a href="stream.kspin">KSPIN</a> structure representing the pin on which to submit a frame.

### -param Mdl [in, optional]

A pointer to a memory descriptor list describing the frame buffer. Optional.

### -param StreamHeader [in, optional]

A pointer to a <a href="stream.ksstream_header">KSSTREAM_HEADER</a> structure. The stream header is copied if this parameter is supplied. Optional.

### -param Context [in, optional]

A pointer to a caller-allocated buffer that is passed to the frame return callback registered through <a href="stream.kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>. This parameter is optional and is solely for the caller's use.

## -returns
Returns STATUS_SUCCESS if frame submission is successful. Otherwise returns an appropriate error code.

## -remarks
The difference between this function and <a href="stream.kspinsubmitframe">KsPinSubmitFrame</a> is that this function will submit a frame using an <a href="wdkgloss.m#wdkgloss.mdl#wdkgloss.mdl"><i>MDL</i></a> structure rather than a data and size argument.

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
<a href="stream.kspinsubmitframe">KsPinSubmitFrame</a>
</dt>
<dt>
<a href="stream.kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinSubmitFrameMdl function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
